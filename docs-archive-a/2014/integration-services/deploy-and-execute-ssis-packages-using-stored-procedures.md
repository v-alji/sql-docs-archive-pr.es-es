---
title: Implementar y ejecutar paquetes SSIS mediante procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749385"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="ea11b-102">Implementar y ejecutar paquetes SSIS mediante procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="ea11b-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="ea11b-103">Al configurar un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para que use el modelo de implementación de proyectos, puede emplear procedimientos almacenados del catálogo de [!INCLUDE[ssIS](../includes/ssis-md.md)] implementar el proyecto y ejecutar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ea11b-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="ea11b-104">Para obtener información acerca del modelo de implementación de proyectos, vea [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ea11b-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="ea11b-105">También puede usar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para implementar el proyecto y ejecutar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="ea11b-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="ea11b-106">Para obtener más información, vea los temas de la sección **Vea también** .</span><span class="sxs-lookup"><span data-stu-id="ea11b-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ea11b-107">Puede generar fácilmente las instrucciones Transact-SQL para los procedimientos almacenados enumerados en el procedimiento siguiente, a excepción de catalog.deploy_project, si hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea11b-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="ea11b-108">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expanda el nodo de **Catálogos de Integration Services** en el Explorador de objetos y navegue hasta el paquete que desea ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ea11b-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="ea11b-109">Haga clic con el botón derecho en el paquete y, después, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="ea11b-110">Según sea necesario, establezca los valores de parámetros, las propiedades del administrador de conexiones y las opciones de la pestaña **Avanzadas** , como el nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="ea11b-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="ea11b-111">Para obtener más información acerca de los niveles de registro, vea [Habilitar el registro para la ejecución de paquetes en el servidor SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea11b-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="ea11b-112">Antes de hacer clic en **Aceptar** para ejecutar el paquete, haga clic en **Script**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="ea11b-113">Transact-SQL aparece en una ventana del Editor de consultas en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea11b-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="ea11b-114">Para implementar y ejecutar un paquete mediante procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="ea11b-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="ea11b-115">Llame a [catalog.deploy_project &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) para implementar el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea11b-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ea11b-116">Para recuperar el contenido binario del [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] archivo de implementación del proyecto, para el parámetro \* \@ project_stream\* , use una instrucción SELECT con la función OPENROWSET y el proveedor de conjuntos de filas bulk.</span><span class="sxs-lookup"><span data-stu-id="ea11b-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="ea11b-117">El proveedor de conjuntos de filas BULK le permite leer datos de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ea11b-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="ea11b-118">El argumento SINGLE_BLOB del proveedor de conjuntos de filas BULK devuelve el contenido del archivo de datos como un conjunto de filas de una sola fila y una sola columna de tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ea11b-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="ea11b-119">Para obtener más información, vea [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea11b-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="ea11b-120">En el ejemplo siguiente, el proyecto SSISPackages_ProjectDeployment se implementa en la carpeta Paquetes SSIS del servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea11b-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="ea11b-121">Los datos binarios se leen del archivo de proyecto (SSISPackage_ProjectDeployment. ISPAC) y se almacenan en el parámetro \* \@ ProjectBinary\* de tipo varbinary (Max).</span><span class="sxs-lookup"><span data-stu-id="ea11b-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="ea11b-122">El valor del parámetro \* \@ ProjectBinary\* se asigna al parámetro \* \@ project_stream\* .</span><span class="sxs-lookup"><span data-stu-id="ea11b-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="ea11b-123">Llame a [catalog.create_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) para crear una instancia de la ejecución de paquetes y llame opcionalmente a [catalog.set_execution_parameter_value &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) para establecer los valores de parámetro en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ea11b-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="ea11b-124">En el ejemplo siguiente, catalog.create_execution crea una instancia de ejecución del package.dtsx contenido en el proyecto SSISPackage_ProjectDeployment.</span><span class="sxs-lookup"><span data-stu-id="ea11b-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="ea11b-125">El proyecto se encuentra en la carpeta SSIS Packages.</span><span class="sxs-lookup"><span data-stu-id="ea11b-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="ea11b-126">El execution_id devuelto por el procedimiento almacenado se emplea en la llamada a catalog.set_execution_parameter_value.</span><span class="sxs-lookup"><span data-stu-id="ea11b-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="ea11b-127">Este segundo procedimiento almacenado establece el parámetro LOGGING_LEVEL en 3 (registro detallado) y establece un parámetro de paquete denominado Parameter1 en un valor de 1.</span><span class="sxs-lookup"><span data-stu-id="ea11b-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="ea11b-128">Para los parámetros como LOGGING_LEVEL, el valor de object_type es 50.</span><span class="sxs-lookup"><span data-stu-id="ea11b-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="ea11b-129">Para los parámetros de paquete, el valor de object_type es 30.</span><span class="sxs-lookup"><span data-stu-id="ea11b-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="ea11b-130">Llame a [catalog.start_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="ea11b-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="ea11b-131">En el ejemplo siguiente, se agrega a Transact-SQL una llamada a catalog.start_execution para iniciar la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="ea11b-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="ea11b-132">Se empela el execution_id devuelto por el procedimiento almacenado catalog.create_execution.</span><span class="sxs-lookup"><span data-stu-id="ea11b-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="ea11b-133">Para implementar un proyecto entre servidores mediante procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="ea11b-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="ea11b-134">Puede implementar un proyecto entre servidores mediante los procedimientos almacenados [catalog.get_project &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) y [catalog.deploy_project &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="ea11b-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="ea11b-135">Debe hacer lo siguiente antes de ejecutar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="ea11b-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="ea11b-136">Cree un objeto de servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="ea11b-136">Create a linked server object.</span></span> <span data-ttu-id="ea11b-137">Para obtener más información, vea [Crear servidores vinculados &#40;motor de base de datos de SQL Server&#41;](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ea11b-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="ea11b-138">En la página **Opciones del servidor** del cuadro de diálogo **Propiedades del servidor vinculado** , establezca **RPC** y **Salida RPC** en **True**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="ea11b-139">Establezca también **Habilitar la promoción de transacciones distribuidas para RPC** en **False**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="ea11b-140">Habilite los parámetros dinámicos del proveedor seleccionado para el servidor vinculado; para ello, expanda el nodo de **Proveedores** en **Servidores vinculados** en el Explorador de objetos, haga clic con el botón derecho en el proveedor y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="ea11b-141">Seleccione **Habilitar** junto a **Parámetro dinámico**.</span><span class="sxs-lookup"><span data-stu-id="ea11b-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="ea11b-142">Confirme que el Coordinador de transacciones distribuidas (DTC) se inicia en ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="ea11b-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="ea11b-143">Llame a catalog.get_project para devolver el contenido binario del proyecto y llame después a catalog.deploy_project.</span><span class="sxs-lookup"><span data-stu-id="ea11b-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="ea11b-144">El valor devuelto por catalog.get_project se inserta en una variable de tabla de tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ea11b-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="ea11b-145">El servidor vinculado no puede devolver resultados que son varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ea11b-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="ea11b-146">En el ejemplo siguiente, catalog.get_project devuelve un contenido binario para el proyecto SSISPackages del servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="ea11b-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="ea11b-147">catalog.deploy_project implementa el proyecto en el servidor local, en la carpeta denominada DestFolder.</span><span class="sxs-lookup"><span data-stu-id="ea11b-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea11b-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea11b-148">See Also</span></span>  
 <span data-ttu-id="ea11b-149">[Implementación de proyectos en Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="ea11b-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="ea11b-150">[Ejecutar un paquete en SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ea11b-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="ea11b-151">Ejecutar un paquete en el servidor SSIS con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea11b-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
