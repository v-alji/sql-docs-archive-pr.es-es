---
title: Programar y depurar el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674213"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="42b40-102">Codificar y depurar el componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="42b40-103">En el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)], el componente Script tiene dos modos: modo de diseño de metadatos y modo de diseño de código.</span><span class="sxs-lookup"><span data-stu-id="42b40-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="42b40-104">Al abrir el **Editor de transformación Script**, el componente escribe en modo de diseño de metadatos, en el que se configuran metadatos y se establecen las propiedades de componentes.</span><span class="sxs-lookup"><span data-stu-id="42b40-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="42b40-105">Después de haber establecido las propiedades del componente de script y configurar la entrada y las salidas en modo de diseño de metadatos, se puede cambiar al modo de diseño de código para escribir un script personalizado.</span><span class="sxs-lookup"><span data-stu-id="42b40-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="42b40-106">Para obtener más información acerca del modo de diseño de metadatos y el modo de diseño de código, vea [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) (Configurar el componente de script en el editor de componentes de script).</span><span class="sxs-lookup"><span data-stu-id="42b40-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="42b40-107">Escribir el script en modo de diseño de código</span><span class="sxs-lookup"><span data-stu-id="42b40-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="42b40-108">Entorno de desarrollo del componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-108">Script Component Development Environment</span></span>
 <span data-ttu-id="42b40-109">Para escribir un script, haga clic en **Editar script** en la página **Script** del **Editor de transformación Script**, para abrir el IDE de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="42b40-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="42b40-110">El IDE de VSTA incluye todas las características estándar del entorno de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET, como el editor de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] con códigos de color, IntelliSense y el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="42b40-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="42b40-111">El código de script se escribe en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="42b40-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="42b40-112">Puede especificar el lenguaje de script estableciendo la propiedad **ScriptLanguage** en el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="42b40-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="42b40-113">Si prefiere utilizar otro lenguaje de programación, puede desarrollar un ensamblado personalizado en el lenguaje seleccionado y utilizar su funcionalidad en el código del componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="42b40-114">El script que crea en el componente de script se almacena en la definición de paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="42b40-115">No hay un archivo de script independiente.</span><span class="sxs-lookup"><span data-stu-id="42b40-115">There is no separate script file.</span></span> <span data-ttu-id="42b40-116">Por consiguiente, el uso del componente de script no afecta a la implementación del paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="42b40-117">Mientras diseña el paquete, el código de script se escribe temporalmente en un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="42b40-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="42b40-118">Dado que almacenar información confidencial en un archivo supone un riesgo potencial para la seguridad, recomendamos que no incluya información confidencial como contraseñas en el código de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="42b40-119">De forma predeterminada, `Option Strict` está deshabilitada en el IDE.</span><span class="sxs-lookup"><span data-stu-id="42b40-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="42b40-120">Estructura del proyecto del componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-120">Script Component Project Structure</span></span>
 <span data-ttu-id="42b40-121">La eficacia del componente de script reside en que puede generar código de infraestructura que reduce la cantidad de código que se debe escribir.</span><span class="sxs-lookup"><span data-stu-id="42b40-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="42b40-122">Esta característica se basa en el hecho de que las entradas y salidas, y sus columnas y propiedades, son fijas y se conocen previamente.</span><span class="sxs-lookup"><span data-stu-id="42b40-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="42b40-123">Por consiguiente, cualquier cambio subsiguiente que se realiza en los metadatos del componente puede invalidar el código que se ha escrito.</span><span class="sxs-lookup"><span data-stu-id="42b40-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="42b40-124">Esto produce errores de compilación durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="42b40-125">Elementos y clases de proyecto en el proyecto del componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="42b40-126">Al cambiar al modo de diseño de código, el IDE de VSTA se abre y muestra el elemento de proyecto `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="42b40-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="42b40-127">El elemento de proyecto `ScriptMain` contiene la clase `ScriptMain` modificable, que actúa como el punto de entrada para el script y que es donde se escribe el código.</span><span class="sxs-lookup"><span data-stu-id="42b40-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="42b40-128">Los elementos de código de la clase varían, dependiendo del lenguaje de programación seleccionado para la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="42b40-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="42b40-129">El proyecto de script contiene dos elementos de proyecto adicionales de solo lectura generados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="42b40-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="42b40-130">El elemento de proyecto `ComponentWrapper`, que contiene tres clases:</span><span class="sxs-lookup"><span data-stu-id="42b40-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="42b40-131">La clase `UserComponent`, que hereda de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> y que contiene los métodos y propiedades que se usarán para procesar datos e interactuar con el paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="42b40-132">La clase `ScriptMain` hereda de la clase `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="42b40-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="42b40-133">Una clase de colección `Connections` que contiene referencias a las conexiones seleccionadas en la página Administrador de conexiones del Editor de Script de transformación.</span><span class="sxs-lookup"><span data-stu-id="42b40-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="42b40-134">Una `Variables` clase de colección que contiene referencias a las variables especificadas en las `ReadOnlyVariable` `ReadWriteVariables` propiedades y en la página **script** del **Editor de transformación script**.</span><span class="sxs-lookup"><span data-stu-id="42b40-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="42b40-135">El `BufferWrapper` elemento de proyecto contiene una clase que hereda de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para cada entrada y salida configuradas en la página **entradas y salidas** del **Editor de transformación script**.</span><span class="sxs-lookup"><span data-stu-id="42b40-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="42b40-136">Cada una de estas clases contiene las propiedades de descriptor de acceso con tipo, que corresponden a las columnas de entrada y salida configuradas, y los búferes de flujo de datos que contienen las columnas.</span><span class="sxs-lookup"><span data-stu-id="42b40-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="42b40-137">Para obtener más información acerca de cómo usar estos objetos, métodos y propiedades, vea [Descripción del modelo de objetos del componente de script](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="42b40-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="42b40-138">Para obtener información acerca de cómo usar los métodos y propiedades de estas clases en un tipo determinado del componente de script, vea la sección [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md) (Ejemplos de componente de script adicionales).</span><span class="sxs-lookup"><span data-stu-id="42b40-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="42b40-139">Los temas de ejemplo también contienen ejemplos de código completos.</span><span class="sxs-lookup"><span data-stu-id="42b40-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="42b40-140">Al configurar el componente de script como una transformación, el elemento de proyecto `ScriptMain` contiene el siguiente código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="42b40-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="42b40-141">La plantilla de código también proporciona información general sobre el componente Script, así como información adicional sobre cómo recuperar y manipular objetos SSIS, como variables, eventos y conexiones.</span><span class="sxs-lookup"><span data-stu-id="42b40-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="42b40-142">Elementos de proyecto adicionales del proyecto del componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="42b40-143">El proyecto del componente de script puede incluir elementos distintos del elemento `ScriptMain` predeterminado.</span><span class="sxs-lookup"><span data-stu-id="42b40-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="42b40-144">Puede agregar clases, módulos, archivos de código y carpetas al proyecto; además puede usar las carpetas para organizar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="42b40-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="42b40-145">Todos los elementos que se agregan se conservan dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="42b40-146">Referencias en el proyecto del componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-146">References in the Script Component Project</span></span>
 <span data-ttu-id="42b40-147">Para agregar referencias a los ensamblados administrados, haga clic con el botón derecho en el proyecto de la tarea Script en el **Explorador de proyectos** y, después, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="42b40-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="42b40-148">Para obtener más información, consulte [Hacer referencia a otros ensamblados en soluciones de scripting](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="42b40-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="42b40-149">Puede ver las referencias de proyecto en el IDE de VSTA en la **Vista de clases** o en el **Explorador de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="42b40-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="42b40-150">Puede abrir cualquiera de estas ventanas en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="42b40-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="42b40-151">Puede agregar una referencia nueva en el menú **Proyecto**, en el **Explorador de proyectos** o en **Vista de clases**.</span><span class="sxs-lookup"><span data-stu-id="42b40-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="42b40-152">Interactuar con el paquete en el componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="42b40-153">El script personalizado que escribe en el componente de script puede obtener acceso y usar variables y administradores de conexión del paquete contenedor, a través de los descriptores de acceso con establecimiento inflexible de tipos en las clases base generadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="42b40-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="42b40-154">Sin embargo, debe configurar tanto las variables como los administradores de conexión antes de escribir en modo de diseño de código, si desea que estén disponibles en su script.</span><span class="sxs-lookup"><span data-stu-id="42b40-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="42b40-155">Puede también provocar eventos y realizar registros desde su código del componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="42b40-156">Los elementos de proyecto generados automáticamente en el proyecto del componente de script, proporcionan los siguientes objetos, métodos y propiedades para que interactúen con el paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="42b40-157">Característica del paquete</span><span class="sxs-lookup"><span data-stu-id="42b40-157">Package Feature</span></span>|<span data-ttu-id="42b40-158">Método de acceso</span><span class="sxs-lookup"><span data-stu-id="42b40-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="42b40-159">variables</span><span class="sxs-lookup"><span data-stu-id="42b40-159">Variables</span></span>|<span data-ttu-id="42b40-160">Usa las propiedades de descriptor de acceso con nombre y tipo en la clase de colección `Variables` del elemento de proyecto `ComponentWrapper`, expuesto a través de la propiedad `Variables` de la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="42b40-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="42b40-161">El método `PreExecute` únicamente puede tener acceso a variables de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="42b40-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="42b40-162">El método `PostExecute` puede tener acceso a variables de solo lectura y de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="42b40-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="42b40-163">Conexiones</span><span class="sxs-lookup"><span data-stu-id="42b40-163">Connections</span></span>|<span data-ttu-id="42b40-164">Usa las propiedades de descriptor de acceso con nombre y tipo en la clase de colección `Connections` del elemento de proyecto `ComponentWrapper`, expuesto a través de la propiedad `Connections` de la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="42b40-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="42b40-165">Eventos</span><span class="sxs-lookup"><span data-stu-id="42b40-165">Events</span></span>|<span data-ttu-id="42b40-166">Genere eventos mediante la <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> propiedad de la `ScriptMain` clase y los métodos **de \<X> activación** de la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interfaz.</span><span class="sxs-lookup"><span data-stu-id="42b40-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="42b40-167">Registro</span><span class="sxs-lookup"><span data-stu-id="42b40-167">Logging</span></span>|<span data-ttu-id="42b40-168">Realiza registros mediante el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> de la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="42b40-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="42b40-169">Depurar el componente de script</span><span class="sxs-lookup"><span data-stu-id="42b40-169">Debugging the Script Component</span></span>
 <span data-ttu-id="42b40-170">Para depurar el código del componente Script, establezca al menos un punto de interrupción en el código y, a continuación, cierre el IDE de VSTA para ejecutar el paquete en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b40-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="42b40-171">Cuando la ejecución del paquete entra en el componente Script, el IDE de VSTA se vuelve a abrir y muestra el código en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="42b40-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="42b40-172">Después de que la ejecución llega al punto de interrupción, puede examinar los valores de variable y completar el código restante.</span><span class="sxs-lookup"><span data-stu-id="42b40-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="42b40-173">No puede depurar un componente Script al ejecutar este último como parte de un paquete secundario que se ejecuta desde una tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="42b40-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="42b40-174">Los puntos de interrupción establecidos en el componente Script del paquete secundario se descartan en estas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="42b40-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="42b40-175">Puede depurar el paquete secundario ejecutándolo normalmente por separado.</span><span class="sxs-lookup"><span data-stu-id="42b40-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="42b40-176">Al depurar un paquete que contiene varios componentes Script, el depurador depura un componente Script.</span><span class="sxs-lookup"><span data-stu-id="42b40-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="42b40-177">El sistema puede depurar otro componente Script si el depurador se completa, como en el caso de un bucle Foreach o un contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="42b40-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="42b40-178">También puede supervisar la ejecución del componente Script con los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="42b40-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="42b40-179">Interrumpa la ejecución y muestre un mensaje modal mediante el `MessageBox.Show` método del espacio de nombres **System. Windows. Forms** .</span><span class="sxs-lookup"><span data-stu-id="42b40-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="42b40-180">(Quite este código después de completar el proceso de depuración.)</span><span class="sxs-lookup"><span data-stu-id="42b40-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="42b40-181">Provoque eventos para los mensajes informativos, advertencias y errores.</span><span class="sxs-lookup"><span data-stu-id="42b40-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="42b40-182">Los métodos FireInformation, FireWarning y FireError muestran la descripción del evento en la ventana **Resultados** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="42b40-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="42b40-183">Sin embargo, el método FireProgress, el método Console.Write y el método Console.WriteLine no muestran ninguna información en la ventana **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="42b40-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="42b40-184">Los mensajes del evento FireProgress aparecen en la pestaña **Progreso** del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42b40-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="42b40-185">Para obtener más información, consulte [Raising Events in the Script Component](../../data-flow/transformations/script-component.md) (Provocar eventos en el componente de script).</span><span class="sxs-lookup"><span data-stu-id="42b40-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="42b40-186">Registre eventos o mensajes definidos por el usuario para los proveedores de registro habilitados.</span><span class="sxs-lookup"><span data-stu-id="42b40-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="42b40-187">Para obtener más información, consulte [Logging in the Script Component](logging-in-the-script-component.md) (Iniciar sesión en el componente de script).</span><span class="sxs-lookup"><span data-stu-id="42b40-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="42b40-188">Si solamente desea examinar la salida de un componente de script configurado como un origen o como una transformación, sin guardar los datos en un destino, puede detener el flujo de datos con una [transformación de recuento de filas](../../data-flow/transformations/row-count-transformation.md) y adjuntar un visor de datos a la salida del componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="42b40-189">Para obtener información acerca de los visores de datos, vea [Depurar el flujo de datos](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="42b40-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="42b40-190">En esta sección</span><span class="sxs-lookup"><span data-stu-id="42b40-190">In This Section</span></span>
 <span data-ttu-id="42b40-191">Para obtener más información acerca de cómo codificar el componente de script, consulte los temas siguientes en esta sección.</span><span class="sxs-lookup"><span data-stu-id="42b40-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="42b40-192">[Descripción del modelo de objetos del componente de script](understanding-the-script-component-object-model.md) Explica cómo utilizar los objetos, métodos y propiedades disponibles en el componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="42b40-193">[Hacer referencia a otros ensamblados en soluciones de scripting](../referencing-other-assemblies-in-scripting-solutions.md) Explica cómo hacer referencia a objetos de la [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] biblioteca de clases en el componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="42b40-194">[Simular una salida de error para el componente de script](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explica cómo simular una salida de error para las filas que generan errores durante el procesamiento por parte del componente de script.</span><span class="sxs-lookup"><span data-stu-id="42b40-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="42b40-195">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="42b40-195">External Resources</span></span>

-   <span data-ttu-id="42b40-196">Entrada de blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661) (Problemas de instalación y configuración de VSTA en instalaciones de SSIS 2008 y R2), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="42b40-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="42b40-197">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="42b40-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="42b40-198">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="42b40-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="42b40-199">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="42b40-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="42b40-200">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="42b40-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="42b40-201">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42b40-201">See Also</span></span>
 [<span data-ttu-id="42b40-202">Configurar el componente de script en el editor de componentes de script</span><span class="sxs-lookup"><span data-stu-id="42b40-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


