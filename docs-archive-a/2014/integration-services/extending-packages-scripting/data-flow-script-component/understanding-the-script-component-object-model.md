---
title: Descripción del modelo de objetos del componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672186"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="17148-102">Descripción del modelo de objetos del componente de script</span><span class="sxs-lookup"><span data-stu-id="17148-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="17148-103">Tal como se describe en [codificar y depurar el componente de script] (.. /Extending-Packages-scripting/Data-Flow-script-Component/Coding-and-Debugging-The-script-Component.MD, el proyecto de componente de script contiene tres elementos de proyecto:</span><span class="sxs-lookup"><span data-stu-id="17148-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="17148-104">El elemento `ScriptMain`, que contiene la clase `ScriptMain` donde se escribe el código.</span><span class="sxs-lookup"><span data-stu-id="17148-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="17148-105">La clase `ScriptMain` hereda de la clase `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="17148-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="17148-106">El elemento `ComponentWrapper`, que contiene la clase `UserComponent`, una instancia de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> que contiene los métodos y propiedades que utilizará para procesar los datos e interactuar con el paquete.</span><span class="sxs-lookup"><span data-stu-id="17148-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="17148-107">El elemento `ComponentWrapper` también contiene las clases de colección `Connections` y `Variables`.</span><span class="sxs-lookup"><span data-stu-id="17148-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="17148-108">El elemento `BufferWrapper`, que contiene clases que hereda de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para cada entrada y salida, así como propiedades con tipo para cada columna.</span><span class="sxs-lookup"><span data-stu-id="17148-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="17148-109">Al escribir el código en el elemento `ScriptMain`, utiliza los objetos, métodos y propiedades que se explican en este tema.</span><span class="sxs-lookup"><span data-stu-id="17148-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="17148-110">Cada uno de los componentes no utilizará todos los métodos que se enumeran aquí; sin embargo, cuando se utilizan, lo hacen en la secuencia mostrada.</span><span class="sxs-lookup"><span data-stu-id="17148-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="17148-111">La clase base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> no contiene ningún código de la implementación para los métodos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="17148-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="17148-112">Por tanto no es necesario, aunque tampoco es perjudicial, que agregue una llamada a la implementación de la clase base en su propia implementación del método.</span><span class="sxs-lookup"><span data-stu-id="17148-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="17148-113">Para obtener información acerca de cómo usar los métodos y propiedades de estas clases en un tipo determinado del componente de script, vea la sección [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md) (Ejemplos de componente de script adicionales).</span><span class="sxs-lookup"><span data-stu-id="17148-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="17148-114">Los temas de ejemplo también contienen ejemplos de código completos.</span><span class="sxs-lookup"><span data-stu-id="17148-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="17148-115">Método AcquireConnections</span><span class="sxs-lookup"><span data-stu-id="17148-115">AcquireConnections Method</span></span>
 <span data-ttu-id="17148-116">Generalmente, los orígenes y destinos deben conectarse a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="17148-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="17148-117">Invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> para recuperar la conexión o la información de conexión del administrador de conexiones adecuado.</span><span class="sxs-lookup"><span data-stu-id="17148-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="17148-118">En el ejemplo siguiente se devuelve `System.Data.SqlClient.SqlConnection` de un administrador de conexiones ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="17148-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="17148-119">En el ejemplo siguiente se devuelve una ruta de acceso completa y el nombre de archivo de un administrador de conexiones de archivos planos y, a continuación, se abre el archivo mediante `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="17148-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="17148-120">Método PreExecute</span><span class="sxs-lookup"><span data-stu-id="17148-120">PreExecute Method</span></span>
 <span data-ttu-id="17148-121">Invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> siempre que tenga que realizar el procesamiento una sola vez antes de iniciar el procesamiento de las filas de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="17148-122">Por ejemplo, en un destino, es posible que desee configurar el comando con parámetros que utilizará el destino para insertar cada fila de datos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="17148-123">Procesar entradas y salidas</span><span class="sxs-lookup"><span data-stu-id="17148-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="17148-124">Procesar entradas</span><span class="sxs-lookup"><span data-stu-id="17148-124">Processing Inputs</span></span>
 <span data-ttu-id="17148-125">Los componentes de script que se configuran como transformaciones o destinos tienen una entrada.</span><span class="sxs-lookup"><span data-stu-id="17148-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="17148-126">Qué proporciona el elemento de proyecto BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="17148-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="17148-127">Para cada entrada que ha configurado, el elemento de proyecto `BufferWrapper` contiene una clase que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> y tiene el mismo nombre que la entrada.</span><span class="sxs-lookup"><span data-stu-id="17148-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="17148-128">Cada clase de búfer de entrada contiene las siguientes propiedades, funciones y métodos:</span><span class="sxs-lookup"><span data-stu-id="17148-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="17148-129">Propiedades de descriptor de acceso con nombre y tipo para cada columna de entrada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="17148-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="17148-130">Estas propiedades son de solo lectura o de lectura y escritura, dependiendo del **Tipo de uso** especificado para la columna en la página **Columnas de entrada** del **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="17148-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="17148-131">Una propiedad **\<column>_IsNull** para cada columna de entrada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="17148-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="17148-132">Esta propiedad también es de solo lectura o de lectura y escritura, dependiendo del **Tipo de uso** especificado para la columna.</span><span class="sxs-lookup"><span data-stu-id="17148-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="17148-133">Un método **DirectRowTo\<outputbuffer>** para cada salida configurada.</span><span class="sxs-lookup"><span data-stu-id="17148-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="17148-134">Utilizará estos métodos al filtrar las filas a una de varias salidas en el mismo `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="17148-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="17148-135">Una función `NextRow` para obtener la siguiente fila de entrada y una función `EndOfRowset` para determinar si se ha procesado el último búfer de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="17148-136">Normalmente no necesita estas funciones al utilizar los métodos de procesamiento de entrada implementados en la clase base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="17148-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="17148-137">En la sección siguiente se proporciona más información sobre la clase base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="17148-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="17148-138">Qué proporciona el elemento de proyecto ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="17148-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="17148-139">El elemento de proyecto ComponentWrapper contiene una clase denominada `UserComponent` que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="17148-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="17148-140">La clase `ScriptMain` donde escribe el código personalizado deriva a su vez de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="17148-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="17148-141">La clase `UserComponent` contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="17148-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="17148-142">Una implementación invalidada del método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="17148-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="17148-143">Éste es el método al que el motor de flujo de datos llama en tiempo de ejecución después del método `PreExecute` y al que se puede llamar varias veces.</span><span class="sxs-lookup"><span data-stu-id="17148-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="17148-144">`ProcessInput`entrega el procesamiento al método \*\* \<inputbuffer> _ProcessInput\*\* .</span><span class="sxs-lookup"><span data-stu-id="17148-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="17148-145">A continuación, el método `ProcessInput` comprueba el fin del búfer de entrada y, si se ha alcanzado, llama al método reemplazable `FinishOutputs` y al método privado `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="17148-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="17148-146">A continuación, el método `MarkOutputsAsFinished` llama a `SetEndOfRowset` en el último búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="17148-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="17148-147">Una implementación que se puede invalidar del método **\<inputbuffer>_ProcessInput**.</span><span class="sxs-lookup"><span data-stu-id="17148-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="17148-148">Esta implementación predeterminada, simplemente, recorre en bucle cada fila de entrada y llama a **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="17148-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="17148-149">Una implementación que se puede invalidar del método **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="17148-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="17148-150">La implementación predeterminada está vacía.</span><span class="sxs-lookup"><span data-stu-id="17148-150">The default implementation is empty.</span></span> <span data-ttu-id="17148-151">Éste es el método que normalmente invalidará para escribir el código personalizado de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="17148-152">Qué debe hacer el código personalizado</span><span class="sxs-lookup"><span data-stu-id="17148-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="17148-153">Puede utilizar los métodos siguientes para procesar la entrada en la clase `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="17148-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="17148-154">Invalide **\<inputbuffer>_ProcessInputRow** para procesar los datos de cada fila de entrada cuando se pase por ellos.</span><span class="sxs-lookup"><span data-stu-id="17148-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="17148-155">Invalide **\<inputbuffer>_ProcessInput** solamente si es necesaria alguna acción adicional mientras se recorren en bucle las filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="17148-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="17148-156">(Por ejemplo, tiene que probar para `EndOfRowset` realizar alguna otra acción una vez procesadas todas las filas). Llame a \*\* \<inputbuffer> _ProcessInputRow\*\* para realizar el procesamiento de filas.</span><span class="sxs-lookup"><span data-stu-id="17148-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="17148-157">Invalide `FinishOutputs` si es necesaria alguna acción adicional en las salidas antes de cerrarlas.</span><span class="sxs-lookup"><span data-stu-id="17148-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="17148-158">El método `ProcessInput` garantiza que las llamadas a estos métodos se realizan en el momento adecuado.</span><span class="sxs-lookup"><span data-stu-id="17148-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="17148-159">Procesar salidas</span><span class="sxs-lookup"><span data-stu-id="17148-159">Processing Outputs</span></span>
 <span data-ttu-id="17148-160">Los componentes de script configurados como orígenes o transformaciones tienen una o más salidas.</span><span class="sxs-lookup"><span data-stu-id="17148-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="17148-161">Qué proporciona el elemento de proyecto BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="17148-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="17148-162">Para cada salida que ha configurado, el elemento de proyecto BufferWrapper contiene una clase que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> y tiene el mismo nombre que la salida.</span><span class="sxs-lookup"><span data-stu-id="17148-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="17148-163">Cada clase de búfer de entrada contiene las siguientes propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="17148-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="17148-164">Propiedades de descriptor de acceso con nombre y tipo de solo escritura para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="17148-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="17148-165">Propiedad de \*\* \<column> _IsNull\*\* de solo escritura para cada columna de salida seleccionada que se puede usar para establecer el valor de la columna en `null` .</span><span class="sxs-lookup"><span data-stu-id="17148-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="17148-166">Un método `AddRow` para agregar una nueva fila vacía al búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="17148-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="17148-167">Un método `SetEndOfRowset` para permitir que el motor de flujo de datos sepa que no se esperan más búferes de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="17148-168">También existe una función `EndOfRowset` para determinar si el búfer actual es el último búfer de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="17148-169">Normalmente no se necesitan estas funciones cuando se usan los métodos de procesamiento de entrada implementados en la `UserComponent` clase base.</span><span class="sxs-lookup"><span data-stu-id="17148-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="17148-170">Qué proporciona el elemento de proyecto ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="17148-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="17148-171">El elemento de proyecto ComponentWrapper contiene una clase denominada `UserComponent` que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="17148-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="17148-172">La clase `ScriptMain` donde escribe el código personalizado deriva a su vez de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="17148-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="17148-173">La clase `UserComponent` contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="17148-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="17148-174">Una implementación invalidada del método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="17148-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="17148-175">El motor de flujo de datos llama a este método antes de `ProcessInput` en tiempo de ejecución y solamente lo llama una vez.</span><span class="sxs-lookup"><span data-stu-id="17148-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="17148-176">`PrimeOutput` entrega el procesamiento al método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="17148-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="17148-177">A continuación, si el componente es un origen (es decir, el componente no tiene ninguna entrada), `PrimeOutput` llama al método reemplazable `FinishOutputs` y al método privado `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="17148-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="17148-178">El método `MarkOutputsAsFinished` llama a `SetEndOfRowset` en el último búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="17148-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="17148-179">Una implementación reemplazable del método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="17148-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="17148-180">La implementación predeterminada está vacía.</span><span class="sxs-lookup"><span data-stu-id="17148-180">The default implementation is empty.</span></span> <span data-ttu-id="17148-181">Éste es el método que normalmente invalidará para escribir el código personalizado de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="17148-182">Qué debe hacer el código personalizado</span><span class="sxs-lookup"><span data-stu-id="17148-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="17148-183">Puede utilizar los métodos siguientes para procesar las salidas en la clase `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="17148-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="17148-184">Invalide `CreateNewOutputRows` solamente si puede agregar y rellenar las filas de salida antes de procesar las filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="17148-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="17148-185">Por ejemplo, puede utilizar `CreateNewOutputRows` en un origen, pero en una transformación con salidas asincrónicas debe llamar a `AddRow` durante o después del procesamiento de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="17148-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="17148-186">Invalide `FinishOutputs` si es necesaria alguna acción adicional en las salidas antes de cerrarlas.</span><span class="sxs-lookup"><span data-stu-id="17148-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="17148-187">El método `PrimeOutput` garantiza que las llamadas a estos métodos se realizan en el momento adecuado.</span><span class="sxs-lookup"><span data-stu-id="17148-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="17148-188">Método PostExecute</span><span class="sxs-lookup"><span data-stu-id="17148-188">PostExecute Method</span></span>
 <span data-ttu-id="17148-189">Invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> cada vez que cuente con procesamiento que se debe realizar solamente una vez después de procesar las filas de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="17148-190">Por ejemplo, en un origen, puede cerrar la clase `System.Data.SqlClient.SqlDataReader` que ha utilizado para cargar datos en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="17148-191">La colección de `ReadWriteVariables` solamente está disponible en el método `PostExecute`.</span><span class="sxs-lookup"><span data-stu-id="17148-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="17148-192">Por consiguiente no puede incrementar directamente el valor de una variable de paquete cuando procesa cada fila de datos.</span><span class="sxs-lookup"><span data-stu-id="17148-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="17148-193">En su lugar, incremente el valor de una variable local y establezca el valor de la variable de paquete en el valor de la variable local en el `PostExecute` método después de que se hayan procesado todos los datos.</span><span class="sxs-lookup"><span data-stu-id="17148-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="17148-194">Método ReleaseConnections</span><span class="sxs-lookup"><span data-stu-id="17148-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="17148-195">Generalmente, los orígenes y destinos deben conectarse a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="17148-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="17148-196">Invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> para cerrar y liberar la conexión abierta previamente en el método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="17148-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="17148-197">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="17148-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="17148-198">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="17148-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="17148-199">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="17148-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="17148-200">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="17148-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="17148-201">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17148-201">See Also</span></span>
 <span data-ttu-id="17148-202">[Configurar el componente de script en el editor de componentes de script](configuring-the-script-component-in-the-script-component-editor.md) [codificar y depurar el componente de script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span><span class="sxs-lookup"><span data-stu-id="17148-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


