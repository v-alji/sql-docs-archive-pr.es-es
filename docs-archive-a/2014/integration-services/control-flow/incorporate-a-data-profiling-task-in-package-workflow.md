---
title: Incorporar una tarea de generación de perfiles de datos en un flujo de trabajo de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671624"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="6ed21-102">Incorporar una tarea de generación de perfiles de datos en un flujo de trabajo de paquetes</span><span class="sxs-lookup"><span data-stu-id="6ed21-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="6ed21-103">La generación de perfiles de datos y la limpieza no son aptos para la aplicación de un proceso automatizado en sus primeras etapas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="6ed21-104">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], el resultado de la tarea de generación de perfiles de datos normalmente requiere un análisis visual y un criterio humano para determinar si las infracciones detectadas son significativas o excesivas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="6ed21-105">Incluso después de reconocer la existencia de problemas relacionados con la calidad de los datos, sigue siendo necesario disponer de un plan minuciosamente diseñado que indique el mejor método para la limpieza.</span><span class="sxs-lookup"><span data-stu-id="6ed21-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="6ed21-106">Sin embargo, una vez establecidos los criterios para la calidad de los datos, es posible que desee automatizar el análisis y la limpieza periódicos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="6ed21-107">Considere estos escenarios:</span><span class="sxs-lookup"><span data-stu-id="6ed21-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="6ed21-108">**Comprobar la calidad de los datos antes de una carga incremental**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="6ed21-109">Use la tarea de generación de perfiles de datos para calcular el perfil de proporción de columnas nulas de los nuevos datos para la columna CustomerName de una tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="6ed21-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="6ed21-110">Si el porcentaje de valores NULL es superior al 20%, envíe al operador un mensaje de correo electrónico que contenga los resultados del perfil y finalice el paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="6ed21-111">En caso contrario, continúe con la carga incremental.</span><span class="sxs-lookup"><span data-stu-id="6ed21-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="6ed21-112">**Automatizar la limpieza cuando se cumplen las condiciones especificadas**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="6ed21-113">Use la tarea de generación de perfiles de datos para calcular el perfil de inclusión de valores de la columna State en una tabla de búsqueda de estados, y el de la columna ZIP Code/Postal Code en una tabla de búsqueda de códigos postales.</span><span class="sxs-lookup"><span data-stu-id="6ed21-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="6ed21-114">Si el nivel de inclusión de los valores de estado es inferior al 80%, pero el de los valores de código postal es superior al 99%, esto indica dos cosas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="6ed21-115">En primer lugar, los datos de estado están dañados.</span><span class="sxs-lookup"><span data-stu-id="6ed21-115">First, the state data is bad.</span></span> <span data-ttu-id="6ed21-116">En segundo lugar, los datos de código postal están en buen estado.</span><span class="sxs-lookup"><span data-stu-id="6ed21-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="6ed21-117">Inicie una tarea Flujo de datos que limpie los datos de estado realizando una búsqueda de los valores de estado correctos a partir de los valores de código postal actuales.</span><span class="sxs-lookup"><span data-stu-id="6ed21-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="6ed21-118">Una vez que disponga de un flujo de trabajo en el que pueda incorporar la tarea Flujo de datos, deberá comprender los pasos requeridos para agregar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="6ed21-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="6ed21-119">En la sección siguiente se describe el proceso general de incorporación de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="6ed21-120">Las dos secciones finales describen cómo conectar la tarea Flujo de datos directamente a un origen de datos o a datos transformados del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="6ed21-121">Definir un flujo de trabajo general para la tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="6ed21-122">En el procedimiento siguiente se describe el método general para usar el resultado de la tarea de generación de perfiles de datos en el flujo de trabajo de un paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="6ed21-123">Para usar el resultado de la tarea de generación de perfiles de datos en un paquete mediante programación</span><span class="sxs-lookup"><span data-stu-id="6ed21-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="6ed21-124">Agregue y configure la tarea de generación de perfiles de datos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="6ed21-125">Configure las variables de paquete que van a contener los valores que desea recuperar de los resultados del perfil.</span><span class="sxs-lookup"><span data-stu-id="6ed21-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="6ed21-126">Agregue y configure una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-126">Add and configure a Script task.</span></span> <span data-ttu-id="6ed21-127">Conecte dicha tarea a la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="6ed21-128">En la tarea Script, escriba el código necesario para leer los valores deseados del archivo de resultados de la tarea de generación de perfiles de datos y rellenar las variables de paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="6ed21-129">En las restricciones de precedencia que conectan la tarea Script a las bifurcaciones de nivel inferior del flujo de trabajo, escriba expresiones que usen los valores de las variables para dirigir el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="6ed21-130">Al incorporar la tarea de generación de perfiles de datos al flujo de trabajo de un paquete, tenga en cuenta estas dos características de dicha tarea:</span><span class="sxs-lookup"><span data-stu-id="6ed21-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="6ed21-131">**Resultado de la tarea**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-131">**Task output**.</span></span> <span data-ttu-id="6ed21-132">La tarea de generación de perfiles de datos escribe su resultado en un archivo o en una variable de paquete en el formato XML, de acuerdo con el esquema DataProfile.xsd.</span><span class="sxs-lookup"><span data-stu-id="6ed21-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="6ed21-133">Por lo tanto, si desea usar los resultados del perfil en el flujo de trabajo condicional del paquete, debe realizar una consulta en los resultados XML.</span><span class="sxs-lookup"><span data-stu-id="6ed21-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="6ed21-134">Para ello, puede usar el lenguaje para consultas Xpath.</span><span class="sxs-lookup"><span data-stu-id="6ed21-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="6ed21-135">Para estudiar la estructura de estos resultados XML, puede abrir un archivo de resultados de ejemplo o el propio esquema.</span><span class="sxs-lookup"><span data-stu-id="6ed21-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="6ed21-136">Para abrir el archivo de salida o el esquema, puede usar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], otro editor XML o un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ed21-137">Algunos de los resultados del perfil que se muestran en el Visor de perfil de datos son valores calculados que no se encuentran directamente en la salida.</span><span class="sxs-lookup"><span data-stu-id="6ed21-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="6ed21-138">Por ejemplo, la salida del perfil de proporción de columnas nulas contiene el número total de filas y el número de filas que contienen valores NULL.</span><span class="sxs-lookup"><span data-stu-id="6ed21-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="6ed21-139">Para obtener la proporción de columnas nulas, debe usar estos dos valores con objeto de calcular el porcentaje de filas que contienen valores NULL.</span><span class="sxs-lookup"><span data-stu-id="6ed21-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="6ed21-140">**Entrada de la tarea**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-140">**Task input**.</span></span> <span data-ttu-id="6ed21-141">La tarea de generación de perfiles de datos obtiene su entrada de tablas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ed21-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="6ed21-142">Por lo tanto, si desea generar perfiles de datos que ya se han cargado y transformado en el flujo de datos, debe guardar en tablas de ensayo los datos que están en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6ed21-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="6ed21-143">En las siguientes secciones se aplica este flujo de trabajo general a la generación de perfiles de datos que proceden directamente de un origen de datos externo o que han sido transformados por la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="6ed21-144">En dichas secciones también se muestra cómo controlar los requisitos de entrada y salida de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="6ed21-145">Conectar directamente la tarea de generación de perfiles de datos a un origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="6ed21-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="6ed21-146">La tarea de generación de perfiles de datos puede generar perfiles de los datos que provienen directamente de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="6ed21-147">Para ilustrar esta capacidad, el ejemplo siguiente usa la tarea de generación de perfiles de datos para calcular un perfil de proporción de columnas nulas en las columnas de la tabla Person.Address de la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ed21-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="6ed21-148">A continuación, el ejemplo utiliza una tarea Script para recuperar los resultados del archivo de resultados y rellenar las variables de paquete que se pueden usar para dirigir el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ed21-149">Se ha seleccionado la columna AddressLine2 para este sencillo ejemplo porque contiene un alto porcentaje de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="6ed21-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="6ed21-150">El ejemplo consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ed21-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="6ed21-151">Configurar los administradores de conexión que se conectan al origen de datos externo y al archivo de resultados que contendrá los resultados del perfil.</span><span class="sxs-lookup"><span data-stu-id="6ed21-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="6ed21-152">Configurar las variables de paquete que contendrán los valores requeridos por la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="6ed21-153">Configurar la tarea de generación de perfiles de datos para calcular el perfil de proporción de columnas nulas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="6ed21-154">Configurar la tarea Script para obtener la salida XML de la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="6ed21-155">Configurar las restricciones de precedencia que controlarán las bifurcaciones de nivel inferior del flujo de trabajo que se ejecutan dependiendo de los resultados de la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="6ed21-156">Configurar los administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="6ed21-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="6ed21-157">En este ejemplo hay dos administradores de conexión:</span><span class="sxs-lookup"><span data-stu-id="6ed21-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="6ed21-158">Un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que se conecta a la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ed21-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="6ed21-159">Un administrador de conexiones de archivos que crea el archivo de resultados que contendrá los resultados de la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="6ed21-160">Para configurar los administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="6ed21-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="6ed21-161">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cree un nuevo paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ed21-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="6ed21-162">Agregue un administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] al paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="6ed21-163">Configure dicho administrador de conexiones de forma que use el Proveedor de datos .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) y se conecte a una instancia disponible de la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ed21-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="6ed21-164">De forma predeterminada, el administrador de conexiones tiene el nombre siguiente: \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="6ed21-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="6ed21-165">Agregue un administrador de conexiones de archivos al paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="6ed21-166">Configure este administrador de conexiones con objeto de crear el archivo de resultados para la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="6ed21-167">En este ejemplo se usa el nombre de archivo DataProfile1.xml.</span><span class="sxs-lookup"><span data-stu-id="6ed21-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="6ed21-168">De forma predeterminada, el administrador de conexiones tiene el mismo nombre que el archivo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="6ed21-169">Configurar las variables de paquete</span><span class="sxs-lookup"><span data-stu-id="6ed21-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="6ed21-170">En este ejemplo se usan dos variables de paquete:</span><span class="sxs-lookup"><span data-stu-id="6ed21-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="6ed21-171">La variable ProfileConnectionName pasa el nombre del administrador de conexiones de archivos a la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="6ed21-172">La variable AddressLine2NullRatio pasa al paquete la proporción de columnas nulas calculada para esta columna por la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="6ed21-173">Para configurar las variables de paquete que almacenarán los resultados del perfil</span><span class="sxs-lookup"><span data-stu-id="6ed21-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="6ed21-174">En la ventana **Variables** , agregue y configure las dos variables de paquete siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ed21-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="6ed21-175">Escriba el nombre, `ProfileConnectionName` , para una de las variables y establezca el tipo de esta variable en **cadena**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="6ed21-176">Escriba el nombre, `AddressLine2NullRatio` , para la otra variable y establezca el tipo de esta variable en **Double**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="6ed21-177">Configurar la tarea de generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="6ed21-178">La tarea de generación de perfiles de datos se debe configurar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ed21-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="6ed21-179">Para que use los datos que el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] especifica como entrada.</span><span class="sxs-lookup"><span data-stu-id="6ed21-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="6ed21-180">Para que lleve a cabo un perfil de proporción de columnas nulas en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ed21-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="6ed21-181">Para que guarde los resultados del perfil en el archivo asociado al administrador de conexiones de archivos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="6ed21-182">Para configurar la tarea de generación de perfiles de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="6ed21-183">Agregue una tarea de generación de perfiles de datos al flujo de control.</span><span class="sxs-lookup"><span data-stu-id="6ed21-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="6ed21-184">Abra el **Editor de tareas de generación de perfiles de datos** para configurar la tarea.</span><span class="sxs-lookup"><span data-stu-id="6ed21-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="6ed21-185">En la página **General** del editor, en **Destino**, seleccione el nombre del administrador de conexiones de archivos configurado previamente.</span><span class="sxs-lookup"><span data-stu-id="6ed21-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="6ed21-186">En la página **Solicitudes de perfil** del editor, cree un nuevo perfil de proporción de columnas nulas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="6ed21-187">En el panel **Propiedades de la solicitud** , en **ConnectionManager**, seleccione el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] configurado previamente.</span><span class="sxs-lookup"><span data-stu-id="6ed21-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="6ed21-188">A continuación, en **TableOrView**, seleccione Person.Address.</span><span class="sxs-lookup"><span data-stu-id="6ed21-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="6ed21-189">Cierre el Editor de tareas de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="6ed21-190">Configurar la tarea Script</span><span class="sxs-lookup"><span data-stu-id="6ed21-190">Configure the Script Task</span></span>  
 <span data-ttu-id="6ed21-191">Debe configurarse la tarea Script para que recupere los resultados del archivo de resultados y rellene las variables de paquete previamente configuradas.</span><span class="sxs-lookup"><span data-stu-id="6ed21-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="6ed21-192">Para configurar la tarea Script</span><span class="sxs-lookup"><span data-stu-id="6ed21-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="6ed21-193">Agregue una tarea Script al flujo de control.</span><span class="sxs-lookup"><span data-stu-id="6ed21-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="6ed21-194">Conecte dicha tarea a la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="6ed21-195">Abra el **Editor de la tarea Script** para configurar la tarea.</span><span class="sxs-lookup"><span data-stu-id="6ed21-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="6ed21-196">En la página **Script** , seleccione el lenguaje de programación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6ed21-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="6ed21-197">A continuación, ponga las dos variables de paquete a disposición del script:</span><span class="sxs-lookup"><span data-stu-id="6ed21-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="6ed21-198">En `ReadOnlyVariables` , seleccione `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="6ed21-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="6ed21-199">En el caso de **ReadWriteVariables**, seleccione `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="6ed21-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="6ed21-200">Seleccione **Editar script** para abrir el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="6ed21-201">Agregue una referencia al espacio de nombres System.Xml.</span><span class="sxs-lookup"><span data-stu-id="6ed21-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="6ed21-202">Escriba el código de ejemplo correspondiente al lenguaje de programación elegido:</span><span class="sxs-lookup"><span data-stu-id="6ed21-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ed21-203">El código de ejemplo incluido en este procedimiento muestra la forma de cargar los resultados de la tarea de generación de perfiles de datos desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="6ed21-204">Para cargar los resultados de la tarea de generación de perfiles de datos desde una variable de paquete, vea el código de ejemplo alternativo que viene a continuación de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6ed21-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="6ed21-205">Cierre el entorno de desarrollo de script y, a continuación, el Editor de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="6ed21-206">Código alternativo: leer los resultados del perfil desde una variable</span><span class="sxs-lookup"><span data-stu-id="6ed21-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="6ed21-207">El procedimiento anterior muestra cómo se carga el resultado de la tarea de generación de perfiles de datos desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="6ed21-208">Sin embargo, un método alternativo consistiría en cargar dicho resultado desde una variable de paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="6ed21-209">Para cargar el resultado desde una variable, debe realizar los cambios siguientes en el código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ed21-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="6ed21-210">Llame al método `LoadXml` de la clase `XmlDocument` en lugar de llamar al método `Load`.</span><span class="sxs-lookup"><span data-stu-id="6ed21-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="6ed21-211">En el Editor de la tarea Script, agregue el nombre de la variable de paquete que contiene los resultados del perfil a la lista `ReadOnlyVariables` de la tarea.</span><span class="sxs-lookup"><span data-stu-id="6ed21-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="6ed21-212">Pase el valor de cadena de la variable al método `LoadXML`, como se muestra en el siguiente código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ed21-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="6ed21-213">(en este ejemplo se usa "ProfileOutput" como nombre de la variable de paquete que contiene los resultados del perfil).</span><span class="sxs-lookup"><span data-stu-id="6ed21-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="6ed21-214">Configurar las restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="6ed21-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="6ed21-215">Se deben configurar las restricciones de precedencia con objeto de que controlen las bifurcaciones de nivel inferior del flujo de trabajo que se ejecutan dependiendo de los resultados de la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="6ed21-216">Para configurar las restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="6ed21-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="6ed21-217">En las restricciones de precedencia que conectan la tarea Script a las bifurcaciones de nivel inferior del flujo de trabajo, escriba expresiones que usen los valores de las variables para dirigir el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="6ed21-218">Por ejemplo, puede establecer el valor de la lista **Operación de evaluación** para la restricción de precedencia en **Expresión y restricción**.</span><span class="sxs-lookup"><span data-stu-id="6ed21-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="6ed21-219">A continuación, puede usar `@AddressLine2NullRatio < .90` como valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="6ed21-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="6ed21-220">Esto hará que el flujo de trabajo siga la ruta seleccionada cuando las tareas previas se ejecuten correctamente, y cuando el porcentaje de valores NULL en la columna seleccionada sea inferior al 90%.</span><span class="sxs-lookup"><span data-stu-id="6ed21-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="6ed21-221">Conectar la tarea de generación de perfiles de datos a los datos transformados del flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="6ed21-222">En lugar de generar perfiles para los datos directamente desde un origen de datos, puede generar dichos perfiles para los datos ya cargados y transformados en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="6ed21-223">Sin embargo, la tarea de generación de perfiles de datos solo funciona con datos persistentes, no con datos almacenados en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6ed21-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="6ed21-224">Por lo tanto, primero debe usar un componente de destino para guardar los datos transformados en una tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ed21-225">Al configurar la tarea de generación de perfiles de datos, debe seleccionar tablas y columnas existentes.</span><span class="sxs-lookup"><span data-stu-id="6ed21-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="6ed21-226">Por consiguiente, debe crear la tabla de ensayo en tiempo de diseño antes de configurar la tarea.</span><span class="sxs-lookup"><span data-stu-id="6ed21-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="6ed21-227">En otras palabras, este escenario no permite utilizar una tabla temporal creada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ed21-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="6ed21-228">Después de guardar los datos en una tabla de ensayo, puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ed21-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="6ed21-229">Usar la tarea de generación de perfiles de datos para generar perfiles de los datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="6ed21-230">Usar una tarea Script para leer los resultados, tal como se ha indicado anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="6ed21-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="6ed21-231">Usar estos resultados para dirigir el flujo de trabajo posterior del paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="6ed21-232">El procedimiento siguiente proporciona el método general para usar la tarea de generación de perfiles de datos con objeto de generar perfiles de los datos transformados por el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="6ed21-233">Muchos de estos pasos son similares a los descritos anteriormente para la generación de perfiles de datos que proceden directamente de un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="6ed21-234">Conviene revisar dichos pasos para obtener más información sobre cómo configurar los distintos componentes.</span><span class="sxs-lookup"><span data-stu-id="6ed21-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="6ed21-235">Para usar la tarea de generación de perfiles de datos en el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="6ed21-236">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cree un paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="6ed21-237">En el flujo de datos, agregue, configure y conecte los orígenes y transformaciones apropiados.</span><span class="sxs-lookup"><span data-stu-id="6ed21-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="6ed21-238">En el flujo de datos, agregue, configure y conecte un componente de destino que guarde los datos transformados en una tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="6ed21-239">En el flujo de control, agregue y configure una tarea de generación de perfiles de datos que calcule los perfiles deseados a partir de los datos transformados de la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="6ed21-240">Conecte dicha tarea a la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="6ed21-241">Configure las variables de paquete que van a contener los valores que desea recuperar de los resultados del perfil.</span><span class="sxs-lookup"><span data-stu-id="6ed21-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="6ed21-242">Agregue y configure una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="6ed21-242">Add and configure a Script task.</span></span> <span data-ttu-id="6ed21-243">Conecte dicha tarea a la tarea de generación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="6ed21-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="6ed21-244">En la tarea Script, escriba el código necesario para leer los valores deseados del resultado de la tarea de generación de perfiles de datos y rellenar las variables de paquete.</span><span class="sxs-lookup"><span data-stu-id="6ed21-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="6ed21-245">En las restricciones de precedencia que conectan la tarea Script a las bifurcaciones de nivel inferior del flujo de trabajo, escriba expresiones que usen los valores de las variables para dirigir el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6ed21-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed21-246">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ed21-246">See Also</span></span>  
 <span data-ttu-id="6ed21-247">[Configuración de la Tarea de generación de perfiles de datos](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="6ed21-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="6ed21-248">Visor de perfil de datos</span><span class="sxs-lookup"><span data-stu-id="6ed21-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
