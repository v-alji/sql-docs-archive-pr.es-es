---
title: Destino de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744794"
---
# <a name="sql-server-destination"></a><span data-ttu-id="f937e-102">SQL Server, destino</span><span class="sxs-lookup"><span data-stu-id="f937e-102">SQL Server Destination</span></span>
  <span data-ttu-id="f937e-103">El destino de SQL Server se conecta a una base de datos local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y realiza una carga masiva de datos en tablas y vistas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f937e-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="f937e-104">No se puede usar el destino de SQL Server en paquetes con acceso a una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f937e-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="f937e-105">En su lugar, los paquetes deben utilizar el destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f937e-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="f937e-106">Para más información, consulte [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f937e-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="f937e-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="f937e-107">Permissions</span></span>  
 <span data-ttu-id="f937e-108">Los usuarios que ejecutan paquetes que incluyen el destino de SQL Server deben tener el permiso Crear objetos globales.</span><span class="sxs-lookup"><span data-stu-id="f937e-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="f937e-109">Para otorgar este permiso a los usuarios, utilice la herramienta Directiva de seguridad local que se abre desde el menú **Herramientas administrativas** .</span><span class="sxs-lookup"><span data-stu-id="f937e-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="f937e-110">Si recibe un mensaje de error al ejecutar un paquete que utiliza el destino de SQL Server, asegúrese de que la cuenta que ejecuta el paquete tiene el permiso Crear objetos globales.</span><span class="sxs-lookup"><span data-stu-id="f937e-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="f937e-111">Inserciones masivas</span><span class="sxs-lookup"><span data-stu-id="f937e-111">Bulk Inserts</span></span>  
 <span data-ttu-id="f937e-112">Si se intenta utilizar el destino de SQL Server para realizar una carga masiva de datos en una base de datos remota de SQL Server, puede recibir un mensaje de error similar al siguiente: "Hay un registro OLE DB disponible.</span><span class="sxs-lookup"><span data-stu-id="f937e-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="f937e-113">Origen: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Resultado: 0x80040E14 Descripción: "No se pudo realizar la carga masiva porque el objeto de asignación de archivos SSIS "Global\DTSQLIMPORT" no se pudo abrir.</span><span class="sxs-lookup"><span data-stu-id="f937e-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="f937e-114">Código de error del sistema operativo 2 (El sistema no encuentra el archivo especificado).</span><span class="sxs-lookup"><span data-stu-id="f937e-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="f937e-115">Asegúrese de que tiene acceso a un servidor local mediante Seguridad de Windows."".</span><span class="sxs-lookup"><span data-stu-id="f937e-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="f937e-116">El destino de SQL Server ofrece la misma inserción de datos de alta velocidad en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que proporciona la tarea Inserción masiva. En cambio, al usar el destino de SQL Server, un paquete puede aplicar transformaciones a los datos de las columnas antes de que estos se carguen en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f937e-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f937e-117">Para cargar los datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], es recomendable usar el destino de SQL Server en lugar del destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f937e-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="f937e-118">Opciones de inserción masiva</span><span class="sxs-lookup"><span data-stu-id="f937e-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="f937e-119">Si el destino de SQL Server usa el modo de acceso de datos de carga rápida, puede especificar las siguientes opciones de carga rápida:</span><span class="sxs-lookup"><span data-stu-id="f937e-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="f937e-120">Mantener los valores de identidad del archivo de datos importado o usar valores exclusivos asignados por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f937e-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f937e-121">Conservar los valores NULL durante la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="f937e-122">Comprobar las restricciones en la tabla o vista de destino durante la operación de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="f937e-123">Adquirir un bloqueo de nivel de tabla durante la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="f937e-124">Ejecutar desencadenadores de inserción definidos en la tabla de destino durante la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="f937e-125">Especificar el número de la primera fila en la entrada que se debe cargar durante la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="f937e-126">Especificar el número de la última fila en la entrada que se debe cargar durante la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="f937e-127">Especificar el número máximo de errores que pueden producirse antes de que se cancele la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="f937e-128">Cada fila que no puede importarse se cuenta como un error.</span><span class="sxs-lookup"><span data-stu-id="f937e-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="f937e-129">Especificar las columnas de la entrada que contienen datos ordenados.</span><span class="sxs-lookup"><span data-stu-id="f937e-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="f937e-130">Para obtener más información sobre las opciones de carga masiva, vea [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f937e-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="f937e-131">Mejoras de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f937e-131">Performance Improvements</span></span>  
 <span data-ttu-id="f937e-132">Para mejorar el rendimiento de una inserción masiva y el acceso a los datos de tablas durante la operación de inserción masiva, se deben cambiar las opciones predeterminadas de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f937e-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="f937e-133">No comprobar las restricciones en la tabla o vista de destino durante la operación de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="f937e-134">No ejecutar desencadenadores de inserción definidos en la tabla de destino durante la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="f937e-135">No aplicar un bloqueo a la tabla.</span><span class="sxs-lookup"><span data-stu-id="f937e-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="f937e-136">De esta manera, la tabla sigue disponible para otros usuarios y aplicaciones durante la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="f937e-137">Configuración del destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f937e-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="f937e-138">Puede configurar el destino de SQL Server de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f937e-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="f937e-139">Especificar la tabla o vista en la que se debe realizar la carga masiva de los datos.</span><span class="sxs-lookup"><span data-stu-id="f937e-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="f937e-140">Personalizar la operación de carga masiva especificando opciones tales como si se deben comprobar restricciones.</span><span class="sxs-lookup"><span data-stu-id="f937e-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="f937e-141">Especificar si todas las filas se confirman en un lote o establecer el número máximo de filas que se confirman como un lote.</span><span class="sxs-lookup"><span data-stu-id="f937e-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="f937e-142">Especificar un tiempo de espera para la operación de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="f937e-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="f937e-143">Este destino usa un administrador de conexiones de OLE DB para conectarse a un origen de datos y el administrador de conexiones especifica el proveedor OLE DB que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="f937e-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="f937e-144">Para más información, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f937e-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f937e-145">Un proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] también proporciona el objeto de origen de datos desde el que se puede crear un administrador de conexiones de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f937e-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="f937e-146">Esto hace que los orígenes de datos y vistas del origen de datos queden a disposición del destino de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f937e-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="f937e-147">El destino de SQL Server tiene una entrada.</span><span class="sxs-lookup"><span data-stu-id="f937e-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="f937e-148">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="f937e-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="f937e-149">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f937e-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f937e-150">Para obtener más información sobre las propiedades que se pueden configurar en el cuadro de diálogo **Editor de destino de SQL Server** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f937e-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f937e-151">Editor de destino de SQL &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="f937e-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="f937e-152">Editor de destino de SQL &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="f937e-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="f937e-153">Editor de destino de SQL &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="f937e-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="f937e-154">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f937e-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="f937e-155">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f937e-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f937e-156">Common Properties</span><span class="sxs-lookup"><span data-stu-id="f937e-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="f937e-157">Propiedades personalizadas del destino SQL Server</span><span class="sxs-lookup"><span data-stu-id="f937e-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="f937e-158">Para obtener más información sobre cómo establecer valores de propiedades, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f937e-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f937e-159">Realizar una carga masiva de datos mediante el destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f937e-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="f937e-160">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f937e-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f937e-161">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f937e-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f937e-162">Realizar una carga masiva de datos mediante el destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f937e-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="f937e-163">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f937e-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="f937e-164">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f937e-164">Related Content</span></span>  
  
-   <span data-ttu-id="f937e-165">Artículo técnico, sobre la [posible aparición del error "No se puede preparar la inserción masiva de SSIS para la inserción de datos" en sistemas habilitados para UAC](https://go.microsoft.com/fwlink/?LinkId=199482), en support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f937e-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="f937e-166">Artículo técnico, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), en msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f937e-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="f937e-167">Artículo técnico sobre cómo [usar SQL Server Integration Services para la carga masiva de datos](https://go.microsoft.com/fwlink/?LinkId=233701), en simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="f937e-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f937e-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f937e-168">See Also</span></span>  
 [<span data-ttu-id="f937e-169">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f937e-169">Data Flow</span></span>](data-flow.md)  
  
  
