---
title: Crear un origen con el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673771"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="89c06-102">Crear un origen con el componente de script</span><span class="sxs-lookup"><span data-stu-id="89c06-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="89c06-103">Los componentes de origen del flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] se usan para cargar datos de un origen de datos y pasarlos a transformaciones y destinos de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="89c06-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="89c06-104">Normalmente la conexión al origen de datos se realiza a través de un administrador de conexiones existente.</span><span class="sxs-lookup"><span data-stu-id="89c06-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="89c06-105">Para obtener información general sobre el componente de script, vea [extender el flujo de datos con el componente de script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="89c06-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="89c06-106">El componente de script y el código de infraestructura que genera simplifican considerablemente el proceso de desarrollo de un componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="89c06-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="89c06-107">Sin embargo, para entender cómo funciona el componente de script, puede resultar útil leer los pasos necesarios para el desarrollo de un componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="89c06-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="89c06-108">Vea la sección [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) (Desarrollo de un componente de flujo de datos personalizado), especialmente el tema [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) (Desarrollo de un componente de origen personalizado).</span><span class="sxs-lookup"><span data-stu-id="89c06-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="89c06-109">Introducción al componente de origen</span><span class="sxs-lookup"><span data-stu-id="89c06-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="89c06-110">Al agregar un componente de script al panel Flujo de datos del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)], se abre el cuadro de diálogo **Seleccionar el tipo de componente de script** y se solicita la selección de un script de origen, destino o transformación.</span><span class="sxs-lookup"><span data-stu-id="89c06-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="89c06-111">En este cuadro de diálogo, seleccione **Origen**.</span><span class="sxs-lookup"><span data-stu-id="89c06-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="89c06-112">Configurar un componente de origen en modo de diseño de metadatos</span><span class="sxs-lookup"><span data-stu-id="89c06-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="89c06-113">Después de seleccionar la opción para crear un componente de origen, configure el componente mediante el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="89c06-114">Para obtener más información, consulte [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md) (Configurar el componente de script en el editor de componentes de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="89c06-115">Un componente de origen de flujo de datos no tiene ninguna entrada y admite una o más salidas.</span><span class="sxs-lookup"><span data-stu-id="89c06-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="89c06-116">La configuración de las salidas del componente es uno de los pasos que debe completar en el modo de diseño de metadatos, mediante el **Editor de transformación Script**, antes de escribir un script personalizado.</span><span class="sxs-lookup"><span data-stu-id="89c06-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="89c06-117">También puede especificar el lenguaje de script mediante el establecimiento de la propiedad **ScriptLanguage** en la página **Script** del **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="89c06-118">Para establecer el lenguaje de script predeterminado para los componentes Script y las tareas de script, utilice la opción **Lenguaje de scripting** en la página **General** del cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="89c06-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="89c06-119">Para obtener más información, vea [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="89c06-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="89c06-120">Agregar administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="89c06-120">Adding Connection Managers</span></span>
 <span data-ttu-id="89c06-121">Normalmente, un componente de origen utiliza un administrador de conexiones existente para conectarse al origen de datos del que carga los datos en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="89c06-122">En la página **Administradores de conexión** del **Editor de transformación Script**, haga clic en **Agregar** para agregar el administrador de conexiones adecuado.</span><span class="sxs-lookup"><span data-stu-id="89c06-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="89c06-123">Sin embargo, un administrador de conexiones solo es una unidad práctica que encapsula y almacena la información necesaria para conectarse a un origen de datos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="89c06-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="89c06-124">Debe escribir su propio código personalizado para cargar o guardar los datos y posiblemente también para abrir y cerrar la conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="89c06-125">Para obtener información general acerca de cómo se utilizan los administradores de conexión con el componente de script, vea [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md) (Conexión a orígenes de datos en el componente de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="89c06-126">Para obtener más información acerca de la página **Administradores de conexión** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md) (Editor de transformación Script [página Administradores de conexión]).</span><span class="sxs-lookup"><span data-stu-id="89c06-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="89c06-127">Configurar salidas y columnas de salida</span><span class="sxs-lookup"><span data-stu-id="89c06-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="89c06-128">Un componente de origen no tiene ninguna entrada y admite una o más salidas.</span><span class="sxs-lookup"><span data-stu-id="89c06-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="89c06-129">En la página **Entradas y salidas** del **Editor de transformación Script**, se ha creado una única salida de forma predeterminada, pero no se ha creado ninguna columna de salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="89c06-130">En esta página del editor, quizá necesite o desee configurar los elementos siguientes.</span><span class="sxs-lookup"><span data-stu-id="89c06-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="89c06-131">Debe agregar y configurar manualmente las columnas de salida para cada salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="89c06-132">Seleccione la carpeta Columnas de salida para cada salida y, a continuación, utilice los botones **Agregar columna** y **Quitar columna** para administrar las columnas de salida de cada salida del componente de origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="89c06-133">Después, hará referencia a las columnas de salida en el script por los nombres que asigna aquí, mediante las propiedades de descriptor de acceso con tipo creadas en el código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c06-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="89c06-134">Puede crear una o varias salidas adicionales, como una salida de error simulada para las filas que contienen valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="89c06-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="89c06-135">Utilice los botones **Agregar salida** y **Quitar salida** para administrar las salidas del componente de origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="89c06-136">Todas las filas de entrada se dirigen a todas las salidas disponibles a menos que también especifique un valor distinto de cero idéntico para la propiedad `ExclusionGroup` de las salidas si desea dirigir cada fila a solo una de las salidas que comparten el mismo valor de `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="89c06-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="89c06-137">El valor entero determinado seleccionado para identificar el elemento `ExclusionGroup` no es significativo.</span><span class="sxs-lookup"><span data-stu-id="89c06-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="89c06-138">También puede utilizar un valor de la propiedad `ExclusionGroup` distinto de cero con una salida única si no desea generar la salida de todas las filas.</span><span class="sxs-lookup"><span data-stu-id="89c06-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="89c06-139">No obstante, en este caso, debe llamar explícitamente al método **DirectRowTo\<outputbuffer>** para cada fila que quiera enviar a la salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="89c06-140">Puede asignar un nombre descriptivo a las salidas.</span><span class="sxs-lookup"><span data-stu-id="89c06-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="89c06-141">Después, hará referencia a las salidas en el script por sus nombres, mediante las propiedades de descriptor de acceso con tipo creadas en el código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c06-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="89c06-142">Normalmente, varias salidas del mismo `ExclusionGroup` tienen las mismas columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="89c06-143">Sin embargo, si crea una salida de error simulada, quizá desee agregar más columnas que almacenen información de error.</span><span class="sxs-lookup"><span data-stu-id="89c06-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="89c06-144">Para obtener información acerca de cómo el motor de flujo de datos procesa las filas de errores, vea [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) (Uso de las salidas de error en un componente de flujo de datos).</span><span class="sxs-lookup"><span data-stu-id="89c06-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="89c06-145">En el componente de script, sin embargo, debe escribir su propio código para llenar las columnas adicionales con la información de error adecuada.</span><span class="sxs-lookup"><span data-stu-id="89c06-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="89c06-146">Para obtener más información, vea [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) (Simular una salida de error para el componente de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="89c06-147">Para obtener más información acerca de la página **Entradas y salidas** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md) (Editor de transformación Script [página Entradas y salidas]).</span><span class="sxs-lookup"><span data-stu-id="89c06-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="89c06-148">Agregar variables</span><span class="sxs-lookup"><span data-stu-id="89c06-148">Adding Variables</span></span>
 <span data-ttu-id="89c06-149">Si hay variables existentes cuyos valores quiere usar en el script, puede agregarlas en los `ReadOnlyVariables` `ReadWriteVariables` campos de propiedades y en la página **script** del **Editor de transformación script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="89c06-150">Al introducir diversas variables en los campos de propiedades, separe los nombres de éstas por comas.</span><span class="sxs-lookup"><span data-stu-id="89c06-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="89c06-151">También puede especificar varias variables si hace clic en el botón de puntos suspensivos (**...**) situado junto a los `ReadOnlyVariables` campos de `ReadWriteVariables` propiedades y y selecciona variables en el cuadro de diálogo **seleccionar variables** .</span><span class="sxs-lookup"><span data-stu-id="89c06-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="89c06-152">Para obtener información general sobre la forma de usar variables con el componente de script, vea [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md) (Uso de variables con el componente de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="89c06-153">Para obtener más información acerca de la página **Script** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md) (Editor de transformación Script [página Script]).</span><span class="sxs-lookup"><span data-stu-id="89c06-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="89c06-154">Generar script en un componente de origen en modo de diseño de código</span><span class="sxs-lookup"><span data-stu-id="89c06-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="89c06-155">Después de configurar los metadatos para el componente, abra el IDE de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) para programar el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="89c06-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="89c06-156">Para abrir VSTA, haga clic en **Editar script** en la página **Script** del **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="89c06-157">Puede escribir el script mediante [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, dependiendo del lenguaje de script seleccionado para la propiedad **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="89c06-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="89c06-158">Para obtener información importante aplicable a todos los tipos de componentes creados mediante el componente de script, vea [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md) (Programación y depuración del componente de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="89c06-159">Descripción del código generado automáticamente</span><span class="sxs-lookup"><span data-stu-id="89c06-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="89c06-160">Al abrir el IDE de VSTA después de crear y configurar un componente de origen, la clase `ScriptMain` modificable aparece en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="89c06-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="89c06-161">El código personalizado se escribe en la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="89c06-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="89c06-162">La clase `ScriptMain` incluye un código auxiliar para el método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="89c06-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="89c06-163">`CreateNewOutputRows` es el método más importante en un componente de origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="89c06-164">Si abre la ventana **Explorador de proyectos** de VSTA, puede ver que el componente de script también ha generado elementos de proyecto y de solo lectura `BufferWrapper` `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="89c06-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="89c06-165">La clase `ScriptMain` hereda de la clase `UserComponent` en el elemento de proyecto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="89c06-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="89c06-166">En tiempo de ejecución, el motor de flujo de datos invoca el método `PrimeOutput` de la clase `UserComponent`, lo que invalida el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> de la clase primaria <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="89c06-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="89c06-167">El método `PrimeOutput` a su vez llama a los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="89c06-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="89c06-168">El método `CreateNewOutputRows`, que se invalida en `ScriptMain` para agregar filas del origen de datos a los búferes de salida, que al principio están vacíos.</span><span class="sxs-lookup"><span data-stu-id="89c06-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="89c06-169">El método `FinishOutputs`, que está vacío de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89c06-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="89c06-170">Invalide este método en `ScriptMain` para realizar cualquier procesamiento que se exija para completar la salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="89c06-171">El método privado `MarkOutputsAsFinished`, que llama al método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> de la clase primaria <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para indicar al motor de flujo de datos que la salida ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="89c06-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="89c06-172">No tiene que llamar explícitamente a `SetEndOfRowset` en su propio código.</span><span class="sxs-lookup"><span data-stu-id="89c06-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="89c06-173">Escribir código personalizado</span><span class="sxs-lookup"><span data-stu-id="89c06-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="89c06-174">Para terminar de crear un componente de origen personalizado, puede escribir script en los siguientes métodos disponibles en la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="89c06-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="89c06-175">Invalide el método `AcquireConnections` para conectarse al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="89c06-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="89c06-176">Extraiga el objeto de conexión, o la información de conexión necesaria, del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="89c06-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="89c06-177">Invalide el método `PreExecute` para cargar datos, si puede cargar al mismo tiempo todos los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="89c06-178">Por ejemplo, puede ejecutar `SqlCommand` en una conexión [!INCLUDE[vstecado](../../includes/vstecado-md.md)] a una base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cargar al mismo tiempo todos los datos de origen en `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="89c06-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="89c06-179">Si debe cargar los datos de origen una fila a la vez (por ejemplo, al leer un archivo de texto), puede cargar los datos mientras recorre las filas en bucle en `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="89c06-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="89c06-180">Utilice el método `CreateNewOutputRows` invalidado para agregar nuevas filas a los búferes de salida vacíos y rellenar los valores de cada columna en las nuevas filas de salida.</span><span class="sxs-lookup"><span data-stu-id="89c06-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="89c06-181">Utilice el método `AddRow` de cada búfer de salida para agregar una nueva fila vacía y, a continuación, establezca los valores de cada columna.</span><span class="sxs-lookup"><span data-stu-id="89c06-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="89c06-182">Normalmente copia los valores de las columnas cargadas del origen externo.</span><span class="sxs-lookup"><span data-stu-id="89c06-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="89c06-183">Invalide el método `PostExecute` para finalizar el procesamiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="89c06-184">Por ejemplo, puede cerrar la clase `SqlDataReader` que utilizó para cargar datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="89c06-185">Invalide el método `ReleaseConnections` para desconectarse del origen de datos externo, si se requiere.</span><span class="sxs-lookup"><span data-stu-id="89c06-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="89c06-186">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="89c06-186">Examples</span></span>
 <span data-ttu-id="89c06-187">En los ejemplos siguientes se muestra el código personalizado que se necesita en la clase `ScriptMain` para crear un componente de origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="89c06-188">En estos ejemplos se usa la tabla **Person. Address** en la `AdventureWorks` base de datos de ejemplo y se pasan la primera y la cuarta columna, las columnas **intAddressID** y **nvarchar (30) City** , a través del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="89c06-189">Estos mismos datos se usan en los ejemplos de origen, transformación y destino de esta sección.</span><span class="sxs-lookup"><span data-stu-id="89c06-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="89c06-190">Se documentan requisitos previos y suposiciones adicionales para cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89c06-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="89c06-191">Ejemplo de origen de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="89c06-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="89c06-192">En este ejemplo se muestra un componente de origen que utiliza un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente para cargar datos de una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="89c06-193">Si desea ejecutar este código de ejemplo, debe configurar el paquete y el componente de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="89c06-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="89c06-194">Cree un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que utilice el proveedor `SqlClient` para conectarse a la base de datos `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="89c06-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="89c06-195">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="89c06-196">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="89c06-197">En la página **Entradas y salidas**, cambie el nombre de la salida predeterminada por un nombre más descriptivo como **MyAddressOutput**, y agregue y configure las dos columnas de salida, **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="89c06-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="89c06-198">Asegúrese de cambiar el tipo de datos de la columna de salida **City** a DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="89c06-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="89c06-199">En la página **Administradores de conexión**, agregue o cree el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] y asígnele un nombre como **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="89c06-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="89c06-200">En la página **Script**, haga clic en **Editar script** y escriba el script que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="89c06-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="89c06-201">A continuación, cierre el entorno de desarrollo de script y el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="89c06-202">Cree y configure un componente de destino, como un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el componente de destino de ejemplo que se muestra en [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) (Crear un destino con el componente de script), que espere las columnas **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="89c06-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="89c06-203">A continuación, conecte el componente de origen al destino.</span><span class="sxs-lookup"><span data-stu-id="89c06-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="89c06-204">(Puede conectar un origen directamente a un destino sin ninguna transformación). Puede crear una tabla de destino ejecutando el siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] comando en la `AdventureWorks` base de datos:</span><span class="sxs-lookup"><span data-stu-id="89c06-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="89c06-205">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89c06-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="89c06-206">Ejemplo de origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="89c06-206">Flat File Source Example</span></span>
 <span data-ttu-id="89c06-207">En este ejemplo se muestra un componente de origen que utiliza un administrador de conexiones de archivos planos existente para cargar datos de un archivo plano en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="89c06-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="89c06-208">Los datos de origen del archivo plano se crean mediante su exportación desde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89c06-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="89c06-209">Si desea ejecutar este código de ejemplo, debe configurar el paquete y el componente de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="89c06-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="89c06-210">Use el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de para exportar la tabla **Person. Address** de la `AdventureWorks` base de datos de ejemplo a un archivo sin formato delimitado por comas.</span><span class="sxs-lookup"><span data-stu-id="89c06-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="89c06-211">En este ejemplo se utiliza el nombre de archivo ExportedAddresses.txt.</span><span class="sxs-lookup"><span data-stu-id="89c06-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="89c06-212">Cree un administrador de conexiones de archivos planos que se conecte al archivo de datos exportado.</span><span class="sxs-lookup"><span data-stu-id="89c06-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="89c06-213">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como origen.</span><span class="sxs-lookup"><span data-stu-id="89c06-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="89c06-214">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="89c06-215">En la página **Entradas y salidas**, cambie el nombre de la salida predeterminada por un nombre más descriptivo, como **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="89c06-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="89c06-216">Agregue y configure las dos columnas de salida, **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="89c06-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="89c06-217">En la página **Administradores de conexión**, agregue o cree el administrador de conexiones de archivos planos utilizando un nombre descriptivo, como **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="89c06-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="89c06-218">En la página **Script**, haga clic en **Editar script** y escriba el script que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="89c06-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="89c06-219">A continuación, cierre el entorno de desarrollo de script y el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="89c06-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="89c06-220">Cree y configure un componente de destino, como un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el componente de destino de ejemplo que se muestra en [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) (Crear un destino con el componente de script).</span><span class="sxs-lookup"><span data-stu-id="89c06-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="89c06-221">A continuación, conecte el componente de origen al destino.</span><span class="sxs-lookup"><span data-stu-id="89c06-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="89c06-222">(Puede conectar un origen directamente a un destino sin ninguna transformación). Puede crear una tabla de destino ejecutando el siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] comando en la `AdventureWorks` base de datos:</span><span class="sxs-lookup"><span data-stu-id="89c06-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="89c06-223">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89c06-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="89c06-224">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="89c06-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="89c06-225">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="89c06-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="89c06-226">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="89c06-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="89c06-227">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="89c06-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="89c06-228">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89c06-228">See Also</span></span>
 <span data-ttu-id="89c06-229">[Crear un destino con el componente de script que](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [desarrolla un componente de origen personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="89c06-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


