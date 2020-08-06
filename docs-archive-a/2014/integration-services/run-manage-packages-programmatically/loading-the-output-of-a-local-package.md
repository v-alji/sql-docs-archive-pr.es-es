---
title: Cargar la salida de un paquete local | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749377"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="46e36-102">Cargar la salida de un paquete local</span><span class="sxs-lookup"><span data-stu-id="46e36-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="46e36-103">Las aplicaciones cliente pueden leer la salida de los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cuando se guarda la salida en destinos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante [!INCLUDE[vstecado](../../includes/vstecado-md.md)] o cuando se guarda en un destino de archivo plano usando las clases del espacio de nombres **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="46e36-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="46e36-104">Sin embargo, una aplicación cliente también puede leer la salida de un paquete directamente de la memoria, sin tener que efectuar un paso intermedio para conservar los datos.</span><span class="sxs-lookup"><span data-stu-id="46e36-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="46e36-105">La clave de esta solución es el `Microsoft.SqlServer.Dts.DtsClient` espacio de nombres, que contiene implementaciones especializadas de las `IDbConnection` `IDbCommand` interfaces, y **IDbDataParameter** del espacio de nombres **System. Data** .</span><span class="sxs-lookup"><span data-stu-id="46e36-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="46e36-106">El ensamblado Microsoft.SqlServer.Dts.DtsClient.dll se instala de forma predeterminada en la carpeta **%Archivos de programa%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="46e36-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="46e36-107">El procedimiento descrito en este tema necesita que la propiedad DelayValidation de la tarea Flujo de datos y de los objetos primarios esté establecida en el valor predeterminado de **False**.</span><span class="sxs-lookup"><span data-stu-id="46e36-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="46e36-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="46e36-108">Description</span></span>
 <span data-ttu-id="46e36-109">Este procedimiento muestra cómo desarrollar una aplicación cliente en código administrado que carga la salida de un paquete con un destino DataReader directamente de la memoria.</span><span class="sxs-lookup"><span data-stu-id="46e36-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="46e36-110">Los pasos resumidos aquí se muestran en el ejemplo de código que figura a continuación.</span><span class="sxs-lookup"><span data-stu-id="46e36-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="46e36-111">Para cargar la salida del paquete de datos en una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="46e36-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="46e36-112">En el paquete, configure un destino DataReader para recibir la salida que desea leer en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="46e36-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="46e36-113">Dé un nombre descriptivo al destino DataReader, dado que utilizará este nombre más adelante en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="46e36-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="46e36-114">Tome nota del nombre del destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="46e36-115">En el proyecto de desarrollo, establezca una referencia al `Microsoft.SqlServer.Dts.DtsClient` espacio de nombres localizando el ensamblado **Microsoft.SqlServer.Dts.DtsClient.dll**.</span><span class="sxs-lookup"><span data-stu-id="46e36-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="46e36-116">De forma predeterminada, este ensamblado se instala en **C:\Archivos de programa\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="46e36-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="46e36-117">Importe el espacio de nombres en el código mediante C# `Using` o la [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="46e36-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="46e36-118">En el código, cree un objeto de tipo `DtsClient.DtsConnection` con una cadena de conexión que contenga los parámetros de línea de comandos requeridos por **dtexec.exe** para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="46e36-119">Para obtener más información, consulte [utilidad dtexec](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="46e36-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="46e36-120">A continuación, abra la conexión con esta cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="46e36-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="46e36-121">También puede emplear la utilidad **dtexecui** para crear visualmente la cadena de conexión necesaria.</span><span class="sxs-lookup"><span data-stu-id="46e36-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="46e36-122">En el código de ejemplo se muestra cómo cargar el paquete del sistema de archivos mediante la sintaxis `/FILE <path and filename>`.</span><span class="sxs-lookup"><span data-stu-id="46e36-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="46e36-123">No obstante, puede también cargar el paquete desde la base de datos MSDB utilizando la sintaxis `/SQL <package name>` o desde el almacén de paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilizando la sintaxis `/DTS \<folder name>\<package name>`.</span><span class="sxs-lookup"><span data-stu-id="46e36-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="46e36-124">Cree un objeto de tipo `DtsClient.DtsCommand` que utiliza el objeto `DtsConnection` creado anteriormente y establezca la propiedad `CommandText` en el nombre del destino DataReader del paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="46e36-125">A continuación, llame al método `ExecuteReader` del objeto de comando para cargar los resultados del paquete en un nuevo DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="46e36-126">Opcionalmente, puede parametrizar indirectamente la salida del paquete utilizando la colección de objetos `DtsDataParameter` en el objeto `DtsCommand` para pasar los valores a las variables definidas en el paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="46e36-127">Dentro del paquete, puede usar estas variables como parámetros de consulta o en expresiones para influir en los resultados devueltos al destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="46e36-128">Debe definir estas variables en el paquete en el espacio de nombres **DtsClient** antes de poder usarlas con el `DtsDataParameter` objeto desde una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="46e36-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="46e36-129">(Puede que tenga que hacer clic en el botón de la barra de herramientas **elegir columnas de variables** en la ventana **variables** para mostrar la columna **espacio de nombres** ). En el código de cliente, cuando se agrega un `DtsDataParameter` a la `Parameters` colección de `DtsCommand` , se omite la referencia de espacio de nombres DtsClient del nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="46e36-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="46e36-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46e36-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="46e36-131">Llame al método `Read` de DataReader repetidamente según sea necesario para recorrer en bucle las filas de datos de salida.</span><span class="sxs-lookup"><span data-stu-id="46e36-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="46e36-132">Utilice los datos, o guárdelos para un uso posterior, en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="46e36-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="46e36-133">El método `Read` de esta implementación de DataReader devuelve `true` una o varias veces después de leer la última fila de datos.</span><span class="sxs-lookup"><span data-stu-id="46e36-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="46e36-134">Esto hace que sea difícil utilizar el código usual que recorre en bucle DataReader mientras `Read` devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="46e36-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="46e36-135">Si el código intenta cerrar DataReader o la conexión después de leer el número esperado de filas, sin una llamada adicional, final al método `Read`, el código producirá una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="46e36-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="46e36-136">Sin embargo, si el código intenta leer los datos en esta última iteración a través de un bucle, cuando `Read` todavía devuelve `true` pero se ha pasado la última fila, el código producirá una excepción `ApplicationException` no controlada con el mensaje, "IDataReader de SSIS se encuentra más allá del final del conjunto de resultados".</span><span class="sxs-lookup"><span data-stu-id="46e36-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="46e36-137">Este comportamiento es distinto del que tienen otras implementaciones de DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="46e36-138">Por consiguiente, si utiliza un bucle para leer las filas de DataReader mientras `Read` devuelve `true`, tiene que escribir el código para capturar, probar y descartar esta `ApplicationException` anticipada en la última llamada correcta al método `Read`.</span><span class="sxs-lookup"><span data-stu-id="46e36-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="46e36-139">O bien, si conoce de antemano el número de filas esperado, puede procesar las filas y, a continuación, llamar al método `Read` un vez más antes de cerrar DataReader y la conexión.</span><span class="sxs-lookup"><span data-stu-id="46e36-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="46e36-140">Llame al método `Dispose` del objeto `DtsCommand`.</span><span class="sxs-lookup"><span data-stu-id="46e36-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="46e36-141">Esto es particularmente importante si ha utilizado cualquier objeto `DtsDataParameter`.</span><span class="sxs-lookup"><span data-stu-id="46e36-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="46e36-142">Cierre DataReader y los objetos de conexión.</span><span class="sxs-lookup"><span data-stu-id="46e36-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="46e36-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46e36-143">Example</span></span>
 <span data-ttu-id="46e36-144">En el ejemplo siguiente se ejecuta un paquete que calcula un valor de agregado único y guarda el valor en un destino DataReader y, a continuación, lee este valor de DataReader y muestra el valor en un cuadro de texto en un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="46e36-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="46e36-145">No se requiere el uso de parámetros al cargar la salida de un paquete en una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="46e36-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="46e36-146">Si no desea usar un parámetro, puede omitir el uso de la variable en el espacio de nombres **DtsClient** y omitir el código que usa el `DtsDataParameter` objeto.</span><span class="sxs-lookup"><span data-stu-id="46e36-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="46e36-147">Para crear el paquete de prueba</span><span class="sxs-lookup"><span data-stu-id="46e36-147">To create the test package</span></span>

1.  <span data-ttu-id="46e36-148">Cree un nuevo paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e36-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="46e36-149">En el código de ejemplo se utiliza "DtsClientWParamPkg.dtsx" como el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="46e36-150">Agregue una variable de tipo String en el espacio de nombres DtsClient.</span><span class="sxs-lookup"><span data-stu-id="46e36-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="46e36-151">En el ejemplo de código se usa Country como el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="46e36-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="46e36-152">(Quizá tenga que hacer clic en el botón de la barra de herramientas **Elegir columnas de variables** de la ventana **Variables** para mostrar la columna **Espacio de nombres**).</span><span class="sxs-lookup"><span data-stu-id="46e36-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="46e36-153">Agregue un administrador de conexiones OLE DB que se conecta a la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e36-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="46e36-154">Agregue una tarea Flujo de datos al paquete y cambie a la superficie de diseño Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="46e36-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="46e36-155">Agregue un origen OLE DB al flujo de datos y configúrelo para utilizar el administrador de conexiones OLE DB creado anteriormente y el comando SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="46e36-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="46e36-156">Haga clic en `Parameters` y, en el cuadro de diálogo **establecer parámetros de consulta** , asigne el parámetro de entrada único de la consulta, Parameter0, a la variable DtsClient:: Country.</span><span class="sxs-lookup"><span data-stu-id="46e36-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="46e36-157">Agregue una transformación Agregado al flujo de datos y conecte la salida del origen OLE DB a la transformación.</span><span class="sxs-lookup"><span data-stu-id="46e36-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="46e36-158">Abra el editor de transformación agregado y configúrelo para que realice una operación "recuento total" en todas las columnas de entrada (\*) y para generar el valor agregado con el alias CustomerCount.</span><span class="sxs-lookup"><span data-stu-id="46e36-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="46e36-159">Agregue un destino DataReader al flujo de datos y conecte la salida de transformación Agregado al destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="46e36-160">En el código de ejemplo se utiliza "DataReaderDest" como el nombre del DataReader.</span><span class="sxs-lookup"><span data-stu-id="46e36-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="46e36-161">Seleccione una columna de entrada disponible única, CustomerCount, para el destino.</span><span class="sxs-lookup"><span data-stu-id="46e36-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="46e36-162">Guarde el paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-162">Save the package.</span></span> <span data-ttu-id="46e36-163">La aplicación de prueba creada a continuación ejecutará el paquete y recuperará la salida directamente de la memoria.</span><span class="sxs-lookup"><span data-stu-id="46e36-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="46e36-164">Para crear la aplicación de prueba</span><span class="sxs-lookup"><span data-stu-id="46e36-164">To create the test application</span></span>

1.  <span data-ttu-id="46e36-165">Cree una nueva aplicación Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="46e36-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="46e36-166">Agregue una referencia al `Microsoft.SqlServer.Dts.DtsClient` espacio de nombres examinando el ensamblado del mismo nombre en **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="46e36-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="46e36-167">Copie y pegue el código muestra siguiente en el módulo de código del formulario.</span><span class="sxs-lookup"><span data-stu-id="46e36-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="46e36-168">Modifique el valor de la `dtexecArgs` variable según sea necesario para que contenga los parámetros de línea de comandos requeridos por **dtexec.exe** para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="46e36-169">En el código muestra se carga el paquete desde el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="46e36-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="46e36-170">Modifique el valor de la `dataReaderName` variable según sea necesario para que contenga el nombre del destino DataReader del paquete.</span><span class="sxs-lookup"><span data-stu-id="46e36-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="46e36-171">Coloque un botón y un cuadro de texto en el formulario.</span><span class="sxs-lookup"><span data-stu-id="46e36-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="46e36-172">En el código de ejemplo se usa `btnRun` como nombre del botón y `txtResults` como el nombre del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="46e36-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="46e36-173">Ejecute la aplicación y haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="46e36-173">Run the application and click the button.</span></span> <span data-ttu-id="46e36-174">Después de una breve pausa mientras el paquete se ejecuta, debería aparecer en el cuadro de texto del formulario el valor agregado calculado por el paquete (el recuento de clientes de Canadá).</span><span class="sxs-lookup"><span data-stu-id="46e36-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="46e36-175">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="46e36-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="46e36-176">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="46e36-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="46e36-177">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="46e36-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="46e36-178">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="46e36-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="46e36-179">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="46e36-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="46e36-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46e36-180">See Also</span></span>
 <span data-ttu-id="46e36-181">[Descripción de las diferencias entre](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) cargar y ejecutar un paquete [local mediante programación](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [cargar y ejecutar un paquete remoto mediante programación](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="46e36-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>


