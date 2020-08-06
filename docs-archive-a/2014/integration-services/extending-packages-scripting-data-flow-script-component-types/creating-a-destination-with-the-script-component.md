---
title: Crear un destino con el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674953"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="93a2d-102">Crear un destino con el componente de script</span><span class="sxs-lookup"><span data-stu-id="93a2d-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="93a2d-103">Los componentes de destino se utilizan en el flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para guardar datos recibidos de orígenes y transformaciones de nivel superior en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="93a2d-104">Por lo general, el componente de destino se conecta al origen de datos a través de un administrador de conexiones existente.</span><span class="sxs-lookup"><span data-stu-id="93a2d-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="93a2d-105">Para obtener información general sobre el componente de script, vea [extender el flujo de datos con el componente de script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="93a2d-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="93a2d-106">El componente de script y el código de infraestructura que genera simplifican considerablemente el proceso de desarrollo de un componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="93a2d-107">Sin embargo, para entender cómo funciona el componente de script, puede resultar útil leer los pasos que debe seguir para desarrollar componentes de flujo de datos personalizados en la sección [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) (Desarrollo de un componente de flujo de datos personalizado) y, en especial, [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) (Desarrollo de un componente de destino personalizado).</span><span class="sxs-lookup"><span data-stu-id="93a2d-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="93a2d-108">Introducción a un componente de destino</span><span class="sxs-lookup"><span data-stu-id="93a2d-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="93a2d-109">Al agregar un componente de script a la pestaña Flujo de datos del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)], se abre el cuadro de diálogo **Seleccionar el tipo de componente de script** y se solicita la selección de un script de **Origen**, **Destino** o **Transformación**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="93a2d-110">En este cuadro de diálogo, seleccione **Destino**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="93a2d-111">A continuación, conecte la salida de una transformación al componente de destino en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a2d-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="93a2d-112">Como prueba, puede conectar un origen directamente a un destino sin ninguna transformación.</span><span class="sxs-lookup"><span data-stu-id="93a2d-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="93a2d-113">Configurar un componente de destino en modo de diseño de metadatos</span><span class="sxs-lookup"><span data-stu-id="93a2d-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="93a2d-114">Después de seleccionar la opción para crear un componente de destino, configure el componente mediante el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="93a2d-115">Para obtener más información, consulte [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md) (Configurar el componente de script en el editor de componentes de script).</span><span class="sxs-lookup"><span data-stu-id="93a2d-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="93a2d-116">Para seleccionar el lenguaje de script que utilizará el destino de script, establezca la propiedad **ScriptLanguage** en la página **Script** del cuadro de diálogo **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="93a2d-117">Para establecer el lenguaje de scripting predeterminado para el componente de script, utilice la opción **Lenguaje de scripting** en la página **General** del cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="93a2d-118">Para obtener más información, vea [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="93a2d-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="93a2d-119">Un componente de destino de flujo de datos tiene una entrada y ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="93a2d-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="93a2d-120">La configuración de la entrada del componente es uno de los pasos que debe completar en el modo de diseño de metadatos, mediante el **Editor de transformación Script**, antes de escribir un script personalizado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="93a2d-121">Agregar administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="93a2d-121">Adding Connection Managers</span></span>
 <span data-ttu-id="93a2d-122">Normalmente, un componente de destino utiliza un administrador de conexiones existente para conectarse al origen de datos donde guarda los datos del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="93a2d-123">En la página **Administradores de conexión** del **Editor de transformación Script**, haga clic en **Agregar** para agregar el administrador de conexiones adecuado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="93a2d-124">Sin embargo, un administrador de conexiones es tan solo una unidad práctica que encapsula y almacena la información necesaria para conectarse a un origen de datos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="93a2d-125">Debe escribir su propio código personalizado para cargar o guardar los datos y posiblemente para abrir y cerrar la conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="93a2d-126">Para obtener información general acerca de cómo se utilizan los administradores de conexión con el componente de script, vea [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md) (Conexión a orígenes de datos en el componente de script).</span><span class="sxs-lookup"><span data-stu-id="93a2d-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="93a2d-127">Para obtener más información acerca de la página **Administradores de conexión** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md) (Editor de transformación Script [página Administradores de conexión]).</span><span class="sxs-lookup"><span data-stu-id="93a2d-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="93a2d-128">Configurar entradas y columnas de entrada</span><span class="sxs-lookup"><span data-stu-id="93a2d-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="93a2d-129">Un componente de destino tiene una entrada y ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="93a2d-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="93a2d-130">En la página **Columnas de entrada** del **Editor de transformación Script**, la lista de columnas muestra las columnas disponibles de la salida del componente de nivel superior en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="93a2d-131">Seleccione las columnas que desea guardar.</span><span class="sxs-lookup"><span data-stu-id="93a2d-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="93a2d-132">Para obtener más información acerca de la página **Columnas de entrada** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md) (Editor de transformación Script [página Columnas de entrada]).</span><span class="sxs-lookup"><span data-stu-id="93a2d-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="93a2d-133">La página **Entradas y salidas** del **Editor de transformación Script** muestra una entrada única, cuyo nombre puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="93a2d-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="93a2d-134">Hará referencia a la entrada por su nombre en el script mediante la propiedad de descriptor de acceso creada en el código generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="93a2d-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="93a2d-135">Para obtener más información acerca de la página **Entradas y salidas** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md) (Editor de transformación Script [página Entradas y salidas]).</span><span class="sxs-lookup"><span data-stu-id="93a2d-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="93a2d-136">Agregar variables</span><span class="sxs-lookup"><span data-stu-id="93a2d-136">Adding Variables</span></span>
 <span data-ttu-id="93a2d-137">Si desea usar variables existentes en el script, puede agregarlas en los `ReadOnlyVariables` campos de propiedades y `ReadWriteVariables` en la página **script** del **Editor de transformación script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="93a2d-138">Cuando agregue varias variables a los campos de propiedades, separe sus nombres con comas.</span><span class="sxs-lookup"><span data-stu-id="93a2d-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="93a2d-139">También puede seleccionar varias variables haciendo clic en el botón de puntos suspensivos (**...**) situado junto a los `ReadOnlyVariables` campos de propiedades y y `ReadWriteVariables` , a continuación, seleccionando las variables en el cuadro de diálogo **seleccionar variables** .</span><span class="sxs-lookup"><span data-stu-id="93a2d-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="93a2d-140">Para obtener información general sobre la forma de usar variables con el componente de script, vea [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md) (Uso de variables con el componente de script).</span><span class="sxs-lookup"><span data-stu-id="93a2d-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="93a2d-141">Para obtener más información acerca de la página **Script** del **Editor de transformación Script**, vea [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md) (Editor de transformación Script [página Script]).</span><span class="sxs-lookup"><span data-stu-id="93a2d-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="93a2d-142">Generar script en un componente de destino en modo de diseño de código</span><span class="sxs-lookup"><span data-stu-id="93a2d-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="93a2d-143">Después de haber configurado los metadatos para el componente, puede escribir un script personalizado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="93a2d-144">En la página **Script** del **Editor de transformación Script**, haga clic en **Editar script** para abrir el IDE de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), donde puede agregar el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="93a2d-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="93a2d-145">El lenguaje de scripting que utilice dependerá de si ha seleccionado [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# como lenguaje de script para la propiedad **ScriptLanguage** en la página **Script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="93a2d-146">Para obtener información importante aplicable a todos los tipos de componentes creados mediante el componente de script, vea [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md) (Programación y depuración del componente de script).</span><span class="sxs-lookup"><span data-stu-id="93a2d-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="93a2d-147">Descripción del código generado automáticamente</span><span class="sxs-lookup"><span data-stu-id="93a2d-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="93a2d-148">Al abrir el IDE de VSTA después de crear y configurar un componente de destino, la clase `ScriptMain` modificable aparece en el editor de código con un código auxiliar para el método `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="93a2d-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="93a2d-149">En la clase `ScriptMain` se escribirá el código personalizado; `ProcessInputRow` es el método más importante de un componente de destino.</span><span class="sxs-lookup"><span data-stu-id="93a2d-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="93a2d-150">Si abre la ventana **Explorador de proyectos** de VSTA, puede ver que el componente de script también ha generado elementos de proyecto y de solo lectura `BufferWrapper` `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="93a2d-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="93a2d-151">La clase `ScriptMain` hereda de la clase `UserComponent` en el elemento de proyecto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="93a2d-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="93a2d-152">En tiempo de ejecución, el motor de flujo de datos invoca el método `ProcessInput` de la clase `UserComponent`, lo que invalida el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> de la clase primaria <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="93a2d-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="93a2d-153">A su vez, el método `ProcessInput` recorre las filas del búfer de entrada y llama al método `ProcessInputRow` una vez por cada fila.</span><span class="sxs-lookup"><span data-stu-id="93a2d-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="93a2d-154">Escribir código personalizado</span><span class="sxs-lookup"><span data-stu-id="93a2d-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="93a2d-155">Para terminar de crear un componente de destino personalizado, puede escribir script en los siguientes métodos disponibles en la clase `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="93a2d-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="93a2d-156">Invalide el método `AcquireConnections` para conectarse al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="93a2d-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="93a2d-157">Extraiga el objeto de conexión, o la información de conexión necesaria, del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="93a2d-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="93a2d-158">Invalide el método `PreExecute` para preparar el almacenamiento de los datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="93a2d-159">Por ejemplo, en este método puede crear y configurar una clase `SqlCommand` y sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="93a2d-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="93a2d-160">Utilice el método `ProcessInputRow` invalidado para copiar cada fila de entrada en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="93a2d-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="93a2d-161">Por ejemplo, para un destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede copiar los valores de columna en los parámetros de `SqlCommand` y ejecutar el comando una vez para cada fila.</span><span class="sxs-lookup"><span data-stu-id="93a2d-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="93a2d-162">Para un destino de archivo plano, puede escribir los valores de cada columna en `StreamWriter`, separándolos mediante el delimitador de columna.</span><span class="sxs-lookup"><span data-stu-id="93a2d-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="93a2d-163">Invalide el método `PostExecute` para desconectarse del origen de datos externo, si se requiere, y para realizar cualquier otra limpieza necesaria.</span><span class="sxs-lookup"><span data-stu-id="93a2d-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="93a2d-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="93a2d-164">Examples</span></span>
 <span data-ttu-id="93a2d-165">Los ejemplos siguientes muestran código que se requiere en la clase `ScriptMain` para crear un componente de destino.</span><span class="sxs-lookup"><span data-stu-id="93a2d-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="93a2d-166">En estos ejemplos se usa la tabla **Person. Address** de la base de datos de `AdventureWorks` ejemplo y se pasan la primera y la cuarta columna, las columnas **int \* AddressID**\* y **nvarchar (30) City** , a través del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="93a2d-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="93a2d-167">Estos mismos datos se usan en los ejemplos de origen, transformación y destino de esta sección.</span><span class="sxs-lookup"><span data-stu-id="93a2d-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="93a2d-168">Se documentan requisitos previos y suposiciones adicionales para cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="93a2d-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="93a2d-169">Ejemplo de destino ADO.NET</span><span class="sxs-lookup"><span data-stu-id="93a2d-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="93a2d-170">En este ejemplo se muestra un componente de destino que utiliza un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente para guardar datos del flujo de datos en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a2d-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="93a2d-171">Si desea ejecutar este código de ejemplo, debe configurar el paquete y el componente de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="93a2d-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="93a2d-172">Cree un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que utilice el proveedor `SqlClient` para conectarse a la base de datos `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="93a2d-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="93a2d-173">Cree una tabla de destino ejecutando el siguiente comando [!INCLUDE[tsql](../../includes/tsql-md.md)] en la base de datos `AdventureWorks`:</span><span class="sxs-lookup"><span data-stu-id="93a2d-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="93a2d-174">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como destino.</span><span class="sxs-lookup"><span data-stu-id="93a2d-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="93a2d-175">Conecte la salida de un origen o transformación de nivel superior al componente de destino en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a2d-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="93a2d-176">(Puede conectar un origen directamente a un destino sin ninguna transformación). Esta salida debe proporcionar datos de la tabla **Person. Address** de la `AdventureWorks` base de datos de ejemplo que contiene al menos las columnas **AddressID** y **City** .</span><span class="sxs-lookup"><span data-stu-id="93a2d-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="93a2d-177">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="93a2d-178">En la página **Columnas de entrada**, seleccione las columnas de entrada **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="93a2d-179">En la página **Entradas y salidas**, cambie el nombre de la entrada por un nombre más descriptivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="93a2d-180">En la página **Administradores de conexión**, agregue o cree el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] con un nombre descriptivo como **MyADONETConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="93a2d-181">En la página **Script**, haga clic en **Editar script** y escriba el script que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="93a2d-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="93a2d-182">A continuación, cierre el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="93a2d-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="93a2d-183">Cierre el **Editor de transformación Script** y ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="93a2d-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="93a2d-184">Ejemplo de destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="93a2d-184">Flat File Destination Example</span></span>
 <span data-ttu-id="93a2d-185">En este ejemplo se muestra un componente de destino que utiliza un administrador de conexiones de archivos planos existente para guardar datos del flujo de datos en un archivo plano.</span><span class="sxs-lookup"><span data-stu-id="93a2d-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="93a2d-186">Si desea ejecutar este código de ejemplo, debe configurar el paquete y el componente de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="93a2d-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="93a2d-187">Cree un administrador de conexiones de archivos planos que conecte a un archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="93a2d-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="93a2d-188">El archivo no tiene que existir; el componente de destino lo creará.</span><span class="sxs-lookup"><span data-stu-id="93a2d-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="93a2d-189">Configure el archivo de destino como un archivo delimitado por comas que contenga las columnas **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="93a2d-190">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como destino.</span><span class="sxs-lookup"><span data-stu-id="93a2d-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="93a2d-191">Conecte la salida de un origen o transformación de nivel superior al componente de destino en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a2d-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="93a2d-192">(Puede conectar un origen directamente a un destino sin ninguna transformación). Esta salida debe proporcionar datos de la tabla **Person. Address** de la base de datos de `AdventureWorks` ejemplo y debe contener al menos las columnas **AddressID** y **City** .</span><span class="sxs-lookup"><span data-stu-id="93a2d-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="93a2d-193">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="93a2d-194">En la página **Columnas de entrada**, seleccione las columnas **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="93a2d-195">En la página **Entradas y salidas**, cambie el nombre de la entrada por un nombre más descriptivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="93a2d-196">En la página **Administradores de conexión**, agregue o cree el administrador de conexiones de archivos planos con un nombre descriptivo como **MyFlatFileDestConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="93a2d-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="93a2d-197">En la página **Script**, haga clic en **Editar script** y escriba el script que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="93a2d-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="93a2d-198">A continuación, cierre el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="93a2d-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="93a2d-199">Cierre el **Editor de transformación Script** y ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="93a2d-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="93a2d-200">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="93a2d-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="93a2d-201">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="93a2d-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="93a2d-202">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="93a2d-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="93a2d-203">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="93a2d-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="93a2d-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93a2d-204">See Also</span></span>
 <span data-ttu-id="93a2d-205">[Crear un origen con el componente de script que](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [desarrolla un componente de destino personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="93a2d-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


