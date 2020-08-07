---
title: Pulsaciones de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744796"
---
# <a name="data-flow-taps"></a><span data-ttu-id="c403a-102">Derivaciones de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="c403a-102">Data Flow Taps</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="c403a-103">presenta una nueva característica que le permite agregar una derivación de datos en la ruta de flujo de datos en tiempo de ejecución y dirigir la salida de la derivación de datos a un archivo externo.</span><span class="sxs-lookup"><span data-stu-id="c403a-103">introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="c403a-104">Para usar esta característica, debe implementar el proyecto de SSIS con el modelo de implementación de proyectos en un servidor de SSIS.</span><span class="sxs-lookup"><span data-stu-id="c403a-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="c403a-105">Después de implementar el paquete en el servidor, debe ejecutar scripts T-SQL en la base de datos SSISDB para agregar derivaciones de datos antes de ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="c403a-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="c403a-106">Este es un escenario de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c403a-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="c403a-107">Cree una instancia de ejecución de un paquete con el procedimiento almacenado [catalog.create_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c403a-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="c403a-108">Para agregar una derivación de datos, use el procedimiento almacenado [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) o [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) .</span><span class="sxs-lookup"><span data-stu-id="c403a-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="c403a-109">Inicie la instancia de ejecución del paquete con [catalog.start_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c403a-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="c403a-110">Este es un script SQL de ejemplo que realiza los pasos descritos en el escenario anterior:</span><span class="sxs-lookup"><span data-stu-id="c403a-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="c403a-111">Los parámetros de nombre de carpeta, nombre de proyecto y nombre de paquete del procedimiento almacenado create_execution corresponden a los nombres de carpeta, proyecto y paquete del catálogo de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="c403a-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="c403a-112">Puede obtener los nombres de carpeta, proyecto y paquete que debe usar en la llamada a create_execution desde SQL Server Management Studio, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="c403a-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="c403a-113">Si no ve el proyecto de SSIS aquí, quizás no haya implementado todavía el proyecto en el servidor de SSIS.</span><span class="sxs-lookup"><span data-stu-id="c403a-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="c403a-114">Haga clic con el botón secundario en el proyecto de SSIS en Visual Studio y, a continuación, haga clic en Implementar para implementar el proyecto en el servidor de SSIS esperado.</span><span class="sxs-lookup"><span data-stu-id="c403a-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="c403a-115">En lugar de escribir instrucciones SQL, puede generar el script de ejecución de paquetes mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c403a-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="c403a-116">Haga clic con el botón derecho en **Package.dtsx** y, después, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c403a-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="c403a-117">Haga clic en el botón **Script** de la barra de herramientas para generar el script.</span><span class="sxs-lookup"><span data-stu-id="c403a-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="c403a-118">Ahora, agregue la instrucción add_data_tap antes de la llamada a start_execution.</span><span class="sxs-lookup"><span data-stu-id="c403a-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="c403a-119">El parámetro task_package_path del procedimiento almacenado add_data_tap corresponde a la propiedad PackagePath de la tarea de flujo de datos en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c403a-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="c403a-120">En Visual Studio, haga clic con el botón derecho en **Tarea Flujo de datos**y, después, haga clic en **Propiedades** para abrir la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="c403a-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="c403a-121">Anote el valor de la propiedad **PackagePath** para usarlo como valor para el parámetro task_package_path en la llamada al procedimiento almacenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c403a-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="c403a-122">El parámetro dataflow_path_id_string del procedimiento almacenado add_data_tap corresponde a la propiedad IdentificationString de la ruta de flujo de datos a la que desea agregar una derivación de datos.</span><span class="sxs-lookup"><span data-stu-id="c403a-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="c403a-123">Para obtener dataflow_path_id_string, haga clic en la ruta de flujo de datos (flecha entre las tareas del flujo de datos) y anote el valor de la propiedad **IdentificationString** de la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="c403a-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="c403a-124">Cuando se ejecuta el script, el archivo de salida se almacena en \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span><span class="sxs-lookup"><span data-stu-id="c403a-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="c403a-125">Si ya existe un archivo con ese nombre, se crea un archivo nuevo con un sufijo (por ejemplo: output[1].txt).</span><span class="sxs-lookup"><span data-stu-id="c403a-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="c403a-126">Como se ha indicado anteriormente, también puede usar el procedimiento almacenado [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid), en lugar de usar el procedimiento almacenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c403a-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="c403a-127">Este procedimiento almacenado toma como parámetro el identificador de la tarea Flujo de datos en lugar de task_package_path.</span><span class="sxs-lookup"><span data-stu-id="c403a-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="c403a-128">Puede obtener el identificador de la tarea Flujo de datos de la ventana Propiedades en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c403a-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="c403a-129">Quitar una derivación de datos</span><span class="sxs-lookup"><span data-stu-id="c403a-129">Removing a data tap</span></span>  
 <span data-ttu-id="c403a-130">Puede quitar una derivación de datos antes de iniciar la ejecución con el procedimiento almacenado [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) .</span><span class="sxs-lookup"><span data-stu-id="c403a-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="c403a-131">Este procedimiento almacenado toma como parámetro el identificador de la derivación de datos, que puede obtener como resultado del procedimiento almacenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="c403a-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="c403a-132">Mostrar todas las derivaciones de datos</span><span class="sxs-lookup"><span data-stu-id="c403a-132">Listing all data taps</span></span>  
 <span data-ttu-id="c403a-133">También puede enumerar todas las derivaciones de datos mediante la vista catalog.execution_data_taps.</span><span class="sxs-lookup"><span data-stu-id="c403a-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="c403a-134">En el ejemplo siguiente se extraen derivaciones de datos para una instancia de ejecución de especificación (Id.: 54).</span><span class="sxs-lookup"><span data-stu-id="c403a-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="c403a-135">Consideraciones sobre el rendimiento</span><span class="sxs-lookup"><span data-stu-id="c403a-135">Performance consideration</span></span>  
 <span data-ttu-id="c403a-136">Al habilitar el nivel de registro detallado y agregar derivaciones de datos aumentan las operaciones de E/S que realiza la solución de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="c403a-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="c403a-137">Por tanto, se recomienda agregar derivaciones de datos solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="c403a-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="c403a-138">Vídeo</span><span class="sxs-lookup"><span data-stu-id="c403a-138">Video</span></span>  
 <span data-ttu-id="c403a-139">En este [vídeo de TechNet](https://technet.microsoft.com/sqlserver/dn600163) se muestra cómo agregar y usar derivaciones de datos en el catálogo de SSISDB de SQL Server 2012, que permiten depurar paquetes mediante programación y capturar los resultados parciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c403a-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="c403a-140">También explica cómo enumerar o quitar estas derivaciones de datos y las prácticas recomendadas para usar derivaciones de datos en paquetes de SSIS.</span><span class="sxs-lookup"><span data-stu-id="c403a-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c403a-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c403a-141">Related Tasks</span></span>  
 [<span data-ttu-id="c403a-142">Depurar el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="c403a-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="c403a-143">Herramientas para solucionar problemas de la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="c403a-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
