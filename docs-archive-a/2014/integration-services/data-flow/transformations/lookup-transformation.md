---
title: Transformación Búsqueda | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptrans.f1
helpviewer_keywords:
- Lookup transformation
- joining columns [Integration Services]
- cache [Integration Services]
- match exactly [Integration Services]
- lookups [Integration Services]
- exact matches [Integration Services]
ms.assetid: de1cc8de-e7af-4727-b5a5-a1f0a739aa09
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 567c5d95c2ee7c15ea5c541f7fe2010d46ba36f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676089"
---
# <a name="lookup-transformation"></a><span data-ttu-id="02f1b-102">Transformación de búsqueda</span><span class="sxs-lookup"><span data-stu-id="02f1b-102">Lookup Transformation</span></span>
  <span data-ttu-id="02f1b-103">La transformación Búsqueda realiza búsquedas mediante la combinación de datos de columnas de entrada con columnas de un conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-103">The Lookup transformation performs lookups by joining data in input columns with columns in a reference dataset.</span></span> <span data-ttu-id="02f1b-104">La búsqueda se utiliza para tener acceso a información adicional en una tabla relacionada que está basada en valores de columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="02f1b-104">You use the lookup to access additional information in a related table that is based on values in common columns.</span></span>  
  
 <span data-ttu-id="02f1b-105">El conjunto de datos de referencia puede ser un archivo caché, una tabla o una vista existente, una tabla nueva o el resultado de una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="02f1b-105">The reference dataset can be a cache file, an existing table or view, a new table, or the result of an SQL query.</span></span> <span data-ttu-id="02f1b-106">La transformación Búsqueda utiliza un administrador de conexiones OLE DB o un administrador de conexiones de caché para conectar con el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-106">The Lookup transformation uses either an OLE DB connection manager or a Cache connection manager to connect to the reference dataset.</span></span> <span data-ttu-id="02f1b-107">Para obtener más información, vea [OLE DB Connection Manager](../../connection-manager/ole-db-connection-manager.md) y [Cache Connection Manager](../../connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-107">For more information, see [OLE DB Connection Manager](../../connection-manager/ole-db-connection-manager.md) and [Cache Connection Manager](../../connection-manager/cache-connection-manager.md)</span></span>  
  
 <span data-ttu-id="02f1b-108">Puede configurar la transformación Búsqueda de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="02f1b-108">You can configure the Lookup transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="02f1b-109">Seleccionar el administrador de conexiones que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="02f1b-109">Select the connection manager that you want to use.</span></span> <span data-ttu-id="02f1b-110">Si desea conectarse a una base de datos, seleccione un administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="02f1b-110">If you want to connect to a database, select an OLE DB connection manager.</span></span> <span data-ttu-id="02f1b-111">Si desea conectarse a un archivo caché, seleccione un administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-111">If you want to connect to a cache file, select a Cache connection manager.</span></span>  
  
-   <span data-ttu-id="02f1b-112">Especificar la tabla o vista que contiene el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-112">Specify the table or view that contains the reference dataset.</span></span>  
  
-   <span data-ttu-id="02f1b-113">Generar una base de datos de referencia al especificar una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="02f1b-113">Generate a reference dataset by specifying an SQL statement.</span></span>  
  
-   <span data-ttu-id="02f1b-114">Especificar las combinaciones entre los datos de entrada y el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-114">Specify joins between the input and the reference dataset.</span></span>  
  
-   <span data-ttu-id="02f1b-115">Agregar columnas del conjunto de datos de referencia a la salida de transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-115">Add columns from the reference dataset to the Lookup transformation output.</span></span>  
  
-   <span data-ttu-id="02f1b-116">Configurar las opciones de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-116">Configure the caching options.</span></span>  
  
 <span data-ttu-id="02f1b-117">La transformación Búsqueda admite los siguientes proveedores de bases de datos para el administrador de conexiones OLE DB:</span><span class="sxs-lookup"><span data-stu-id="02f1b-117">The Lookup transformation supports the following database providers for the OLE DB connection manager:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="02f1b-118">Oracle</span><span class="sxs-lookup"><span data-stu-id="02f1b-118">Oracle</span></span>  
  
-   <span data-ttu-id="02f1b-119">DB2</span><span class="sxs-lookup"><span data-stu-id="02f1b-119">DB2</span></span>  
  
 <span data-ttu-id="02f1b-120">La transformación Búsqueda intenta realizar una combinación de igualdad entre valores de la entrada de la transformación y valores del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-120">The Lookup transformation tries to perform an equi-join between values in the transformation input and values in the reference dataset.</span></span> <span data-ttu-id="02f1b-121">Una combinación de igualdad quiere decir que cada fila de la entrada de transformación debe coincidir con, al menos, una fila del conjunto de datos de referencia. Si una combinación de no es posible, la transformación Búsqueda realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="02f1b-121">(An equi-join means that each row in the transformation input must match at least one row from the reference dataset.) If an equi-join is not possible, the Lookup transformation takes one of the following actions:</span></span>  
  
-   <span data-ttu-id="02f1b-122">Si no hay ninguna entrada correspondiente en el conjunto de datos de referencia, no se produce ninguna combinación.</span><span class="sxs-lookup"><span data-stu-id="02f1b-122">If there is no matching entry in the reference dataset, no join occurs.</span></span> <span data-ttu-id="02f1b-123">De forma predeterminada, la transformación Búsqueda trata como errores las filas sin entradas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="02f1b-123">By default, the Lookup transformation treats rows without matching entries as errors.</span></span> <span data-ttu-id="02f1b-124">Sin embargo, la transformación Búsqueda se puede configurar para redirigir dichas filas a un resultado no coincidente.</span><span class="sxs-lookup"><span data-stu-id="02f1b-124">However, you can configure the Lookup transformation to redirect such rows to a no match output.</span></span> <span data-ttu-id="02f1b-125">Para más información, vea [Editor de transformación Búsqueda &#40;página General&#41;](../../lookup-transformation-editor-general-page.md) y [Editor de transformación Búsqueda &#40;página Salida de error&#41;](../../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-125">For more information, see [Lookup Transformation Editor &#40;General Page&#41;](../../lookup-transformation-editor-general-page.md) and [Lookup Transformation Editor &#40;Error Output Page&#41;](../../lookup-transformation-editor-error-output-page.md).</span></span>  
  
-   <span data-ttu-id="02f1b-126">Si hay varias coincidencias en la tabla de referencia, la transformación Búsqueda devuelve solo la primera coincidencia devuelta por la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-126">If there are multiple matches in the reference table, the Lookup transformation returns only the first match returned by the lookup query.</span></span> <span data-ttu-id="02f1b-127">Si se encuentran varias coincidencias, la transformación Búsqueda genera un error o advertencia solo cuando la transformación se ha configurado para cargar todo el conjunto de datos de referencia en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-127">If multiple matches are found, the Lookup transformation generates an error or warning only when the transformation has been configured to load all the reference dataset into the cache.</span></span> <span data-ttu-id="02f1b-128">En este caso, la transformación Búsqueda genera una advertencia cuando detecta varias coincidencias mientras la transformación llena la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-128">In this case, the Lookup transformation generates a warning when the transformation detects multiple matches as the transformation fills the cache.</span></span>  
  
 <span data-ttu-id="02f1b-129">La combinación puede ser compuesta, lo que indica que pueden combinarse varias columnas de la entrada de transformación con columnas del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-129">The join can be a composite join, which means that you can join multiple columns in the transformation input to columns in the reference dataset.</span></span> <span data-ttu-id="02f1b-130">La transformación admite la combinación de columnas con cualquier tipo de datos, a excepción de DT_R4, DT_R8, DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="02f1b-130">The transformation supports join columns with any data type, except for DT_R4, DT_R8, DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="02f1b-131">Para obtener más información, vea [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-131">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="02f1b-132">Normalmente, los valores del conjunto de datos de referencia se agregan a la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="02f1b-132">Typically, values from the reference dataset are added to the transformation output.</span></span> <span data-ttu-id="02f1b-133">Por ejemplo, la transformación Búsqueda puede extraer un nombre de producto de una tabla mediante un valor de una columna de entrada y, después, agregar el nombre del producto a la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="02f1b-133">For example, the Lookup transformation can extract a product name from a table using a value from an input column, and then add the product name to the transformation output.</span></span> <span data-ttu-id="02f1b-134">Los valores de la tabla de referencia pueden reemplazar valores de columnas o agregarse a nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="02f1b-134">The values from the reference table can replace column values or can be added to new columns.</span></span>  
  
 <span data-ttu-id="02f1b-135">Las búsquedas realizadas por la transformación Búsqueda distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="02f1b-135">The lookups performed by the Lookup transformation are case sensitive.</span></span> <span data-ttu-id="02f1b-136">Para evitar errores de búsqueda producidos por diferencias entre mayúsculas y minúsculas en los datos, utilice primero la transformación Mapa de caracteres para convertir los datos en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="02f1b-136">To avoid lookup failures that are caused by case differences in data, first use the Character Map transformation to convert the data to uppercase or lowercase.</span></span> <span data-ttu-id="02f1b-137">A continuación, incluya las funciones UPPER o LOWER en la instrucción SQL que genera la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-137">Then, include the UPPER or LOWER functions in the SQL statement that generates the reference table.</span></span> <span data-ttu-id="02f1b-138">Para más información, vea [Transformación Mapa de caracteres](character-map-transformation.md), [UPPER &#40;Transact-SQL&#41;](/sql/t-sql/functions/upper-transact-sql) y [LOWER &#40;Transact-SQL&#41;](/sql/t-sql/functions/lower-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02f1b-138">For more information, see [Character Map Transformation](character-map-transformation.md), [UPPER &#40;Transact-SQL&#41;](/sql/t-sql/functions/upper-transact-sql), and [LOWER &#40;Transact-SQL&#41;](/sql/t-sql/functions/lower-transact-sql).</span></span>  
  
 <span data-ttu-id="02f1b-139">La transformación Búsqueda tiene las entradas y resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="02f1b-139">The Lookup transformation has the following inputs and outputs:</span></span>  
  
-   <span data-ttu-id="02f1b-140">Entrada.</span><span class="sxs-lookup"><span data-stu-id="02f1b-140">Input.</span></span>  
  
-   <span data-ttu-id="02f1b-141">Resultado coincidente.</span><span class="sxs-lookup"><span data-stu-id="02f1b-141">Match output.</span></span> <span data-ttu-id="02f1b-142">El resultado coincidente administra las filas de la entrada de transformación que coinciden como mínimo con una entrada del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-142">The match output handles the rows in the transformation input that match at least one entry in the reference dataset.</span></span>  
  
-   <span data-ttu-id="02f1b-143">Resultado no coincidente.</span><span class="sxs-lookup"><span data-stu-id="02f1b-143">No Match output.</span></span> <span data-ttu-id="02f1b-144">El resultado no coincidente administra las filas de la entrada que no coinciden como mínimo con una entrada del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-144">The no match output handles rows in the input that do not match at least one entry in the reference dataset.</span></span> <span data-ttu-id="02f1b-145">Si configura la transformación Búsqueda para que trate como errores las filas sin entradas coincidentes, las filas se redirigirán a la salida de errores.</span><span class="sxs-lookup"><span data-stu-id="02f1b-145">If you configure the Lookup transformation to treat the rows without matching entries as errors, the rows are redirected to the error output.</span></span> <span data-ttu-id="02f1b-146">En los demás casos, la transformación redirigiría dichas filas al resultado no coincidente.</span><span class="sxs-lookup"><span data-stu-id="02f1b-146">Otherwise, the transformation would redirect those rows to the no match output.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02f1b-147">En [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)], la transformación Búsqueda solo tenía un resultado.</span><span class="sxs-lookup"><span data-stu-id="02f1b-147">In [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)], the Lookup transformation had only one output.</span></span> <span data-ttu-id="02f1b-148">Para obtener más información sobre cómo ejecutar una transformación búsqueda creada en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , vea actualización de [transformaciones de búsqueda](../../../sql-server/install/upgrade-lookup-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-148">For more information about how to run a Lookup transformation that was created in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], see [Upgrade Lookup Transformations](../../../sql-server/install/upgrade-lookup-transformations.md).</span></span>  
  
-   <span data-ttu-id="02f1b-149">Resultado de errores</span><span class="sxs-lookup"><span data-stu-id="02f1b-149">Error output.</span></span>  
  
## <a name="caching-the-reference-dataset"></a><span data-ttu-id="02f1b-150">Almacenar en caché el conjunto de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="02f1b-150">Caching the Reference Dataset</span></span>  
 <span data-ttu-id="02f1b-151">Una caché en memoria almacena el conjunto de datos de referencia y una tabla hash que indiza los datos.</span><span class="sxs-lookup"><span data-stu-id="02f1b-151">An in-memory cache stores the reference dataset and stores a hash table that indexes the data.</span></span> <span data-ttu-id="02f1b-152">La memoria caché permanece en la memoria hasta que se completa la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="02f1b-152">The cache remains in memory until the execution of the package is completed.</span></span> <span data-ttu-id="02f1b-153">Puede guardar la memoria caché en un archivo caché (.caw).</span><span class="sxs-lookup"><span data-stu-id="02f1b-153">You can persist the cache to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="02f1b-154">Al conservar la memoria caché en un archivo, el sistema la carga con más rapidez.</span><span class="sxs-lookup"><span data-stu-id="02f1b-154">When you persist the cache to a file, the system loads the cache faster.</span></span> <span data-ttu-id="02f1b-155">De esta forma, se mejora el rendimiento de la transformación Búsqueda y del paquete.</span><span class="sxs-lookup"><span data-stu-id="02f1b-155">This improves the performance of the Lookup transformation and the package.</span></span> <span data-ttu-id="02f1b-156">Recuerde que cuando utiliza un archivo caché, está trabajando con datos que no están tan actualizados como los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="02f1b-156">Remember, that when you use a cache file, you are working with data that is not as current as the data in the database.</span></span>  
  
 <span data-ttu-id="02f1b-157">A continuación se describen otras ventajas relacionadas con guardar la memoria caché en un archivo:</span><span class="sxs-lookup"><span data-stu-id="02f1b-157">The following are additional benefits of persisting the cache to a file:</span></span>  
  
-   <span data-ttu-id="02f1b-158">***El archivo caché se puede compartir entre varios paquetes. Para más información, vea***  [Implementar una transformación de búsqueda en el modo de caché completa mediante el Administrador de conexiones de caché](../../connection-manager/lookup-transformation-full-cache-mode-cache-connection-manager.md)  ***.***</span><span class="sxs-lookup"><span data-stu-id="02f1b-158">***Share the cache file between multiple packages. For more information, see***  [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-cache-connection-manager.md)  ***.***</span></span>  
  
-   <span data-ttu-id="02f1b-159">El archivo caché se puede implementar con un paquete.</span><span class="sxs-lookup"><span data-stu-id="02f1b-159">Deploy the cache file with a package.</span></span> <span data-ttu-id="02f1b-160">***De esta forma, podrá utilizar los datos en varios equipos.***</span><span class="sxs-lookup"><span data-stu-id="02f1b-160">***You can then use the data on multiple computers.***</span></span> <span data-ttu-id="02f1b-161">Para obtener información, vea [Cómo crear e implementar una memoria caché para la transformación Búsqueda](create-and-deploy-a-cache-for-the-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-161">For more information, see [Create and Deploy a Cache for the Lookup Transformation](create-and-deploy-a-cache-for-the-lookup-transformation.md).</span></span>  
  
-   <span data-ttu-id="02f1b-162">Usar el origen de archivo sin formato para leer datos del archivo caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-162">Use the Raw File source to read data from the cache file.</span></span> <span data-ttu-id="02f1b-163">A continuación, puede utilizar otros componentes de flujo de datos para transformar o mover los datos.</span><span class="sxs-lookup"><span data-stu-id="02f1b-163">You can then use other data flow components to transform or move the data.</span></span> <span data-ttu-id="02f1b-164">Para más información, consulte [Raw File Source](../raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-164">For more information, see [Raw File Source](../raw-file-source.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02f1b-165">El administrador de conexiones de caché no admite archivos caché creados o modificados mediante el destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="02f1b-165">The Cache connection manager does not support cache files that are created or modified by using the Raw File destination.</span></span>  
  
-   <span data-ttu-id="02f1b-166">Puede llevar a cabo operaciones y atributos de conjunto en el archivo caché utilizando la tarea Sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="02f1b-166">Perform operations and set attributes on the cache file by using the File System task.</span></span> <span data-ttu-id="02f1b-167">Para obtener más información, vea [File System Task](../../control-flow/file-system-task.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-167">For more information, see and [File System Task](../../control-flow/file-system-task.md).</span></span>  
  
 <span data-ttu-id="02f1b-168">A continuación se enumeran las opciones de almacenamiento en caché:</span><span class="sxs-lookup"><span data-stu-id="02f1b-168">The following are the caching options:</span></span>  
  
-   <span data-ttu-id="02f1b-169">El conjunto de datos de referencia se genera mediante una tabla, vista o consulta SQL y se carga en la memoria caché antes de que se ejecute la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-169">The reference dataset is generated by using a table, view, or SQL query and loaded into cache, before the Lookup transformation runs.</span></span> <span data-ttu-id="02f1b-170">Puede usar el administrador de conexiones OLE DB para tener acceso al conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="02f1b-170">You use the OLE DB connection manager to access the dataset.</span></span>  
  
     <span data-ttu-id="02f1b-171">Esta opción de almacenamiento en caché es compatible con la opción de almacenamiento en caché completa disponible para la transformación Búsqueda en [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f1b-171">This caching option is compatible with the full caching option that is available for the Lookup transformation in [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="02f1b-172">El conjunto de datos de referencia se genera a partir de un origen de datos conectado al flujo de datos o de un archivo caché, y se carga en la memoria caché antes de que se ejecute la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-172">The reference dataset is generated from a connected data source in the data flow or from a cache file, and is loaded into cache before the Lookup transformation runs.</span></span> <span data-ttu-id="02f1b-173">Para tener acceso al conjunto de datos puede usar el administrador de conexiones de caché o la transformación Caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-173">You use the Cache connection manager, and, optionally, the Cache transformation, to access the dataset.</span></span> <span data-ttu-id="02f1b-174">Para obtener más información, consulte [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) y [Cache Transform](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="02f1b-174">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
-   <span data-ttu-id="02f1b-175">El conjunto de datos de referencia se genera mediante una tabla, vista o consulta SQL durante la ejecución de la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-175">The reference dataset is generated by using a table, view, or SQL query during the execution of the Lookup transformation.</span></span> <span data-ttu-id="02f1b-176">Las filas con entradas coincidentes en el conjunto de datos de referencia y las que no tienen entradas coincidentes se cargan en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-176">The rows with matching entries in the reference dataset and the rows without matching entries in the dataset are loaded into cache.</span></span>  
  
     <span data-ttu-id="02f1b-177">Cuando se supera el tamaño de la memoria caché, la transformación Búsqueda quita automáticamente de la memoria caché las filas utilizadas con menor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="02f1b-177">When the memory size of the cache is exceeded, the Lookup transformation automatically removes the least frequently used rows from the cache.</span></span>  
  
     <span data-ttu-id="02f1b-178">Esta opción de almacenamiento en caché es compatible con la opción de almacenamiento en caché parcial disponible para la transformación Búsqueda en [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f1b-178">This caching option is compatible with the partial caching option that is available for the Lookup transformation in [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="02f1b-179">El conjunto de datos de referencia se genera mediante una tabla, vista o consulta SQL durante la ejecución de la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-179">The reference dataset is generated by using a table, view, or SQL query during the execution of the Lookup transformation.</span></span> <span data-ttu-id="02f1b-180">No se almacenan datos en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-180">No data is cached.</span></span>  
  
     <span data-ttu-id="02f1b-181">Esta opción de almacenamiento en caché es compatible con la opción sin almacenamiento en caché disponible para la transformación Búsqueda en [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f1b-181">This caching option is compatible with the no caching option that is available for the Lookup transformation in [!INCLUDE[ssISversion2005](../../../includes/ssisversion2005-md.md)].</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="02f1b-182">y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] difieren en el modo en que comparan cadenas.</span><span class="sxs-lookup"><span data-stu-id="02f1b-182">and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differ in the way they compare strings.</span></span> <span data-ttu-id="02f1b-183">Si la transformación Búsqueda se configura para cargar el conjunto de datos de referencia en la memoria caché antes de que se ejecute la transformación Búsqueda, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] lleva a cabo la comparación de búsqueda en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-183">If the Lookup transformation is configured to load the reference dataset into cache before the Lookup transformation runs, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] does the lookup comparison in the cache.</span></span> <span data-ttu-id="02f1b-184">En caso contrario, la operación de búsqueda utiliza una instrucción SQL con parámetros y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] realiza la comparación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02f1b-184">Otherwise, the lookup operation uses a parameterized SQL statement and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does the lookup comparison.</span></span> <span data-ttu-id="02f1b-185">Por lo tanto, es posible que la transformación Búsqueda devuelva un número de coincidencias diferentes a partir de la misma tabla de búsqueda, en función del tipo de caché.</span><span class="sxs-lookup"><span data-stu-id="02f1b-185">This means that the Lookup transformation might return a different number of matches from the same lookup table depending on the cache type.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="02f1b-186">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="02f1b-186">Related Tasks</span></span>  
 <span data-ttu-id="02f1b-187">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="02f1b-187">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="02f1b-188">Para obtener información detallada, vea los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="02f1b-188">For more details, see the following topics.</span></span>  
  
-   [<span data-ttu-id="02f1b-189">Implementar una búsqueda en modo No hay caché o Caché parcial</span><span class="sxs-lookup"><span data-stu-id="02f1b-189">Implement a Lookup in No Cache or Partial Cache Mode</span></span>](implement-a-lookup-in-no-cache-or-partial-cache-mode.md)  
  
-   [<span data-ttu-id="02f1b-190">Implementar una transformación de búsqueda en el modo de caché completa mediante el Administrador de conexiones de caché</span><span class="sxs-lookup"><span data-stu-id="02f1b-190">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](../../connection-manager/lookup-transformation-full-cache-mode-cache-connection-manager.md)  
  
-   [<span data-ttu-id="02f1b-191">Implementar una transformación Búsqueda en el modo de caché completa mediante el Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="02f1b-191">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="02f1b-192">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="02f1b-192">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="02f1b-193">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="02f1b-193">Related Content</span></span>  
  
-   <span data-ttu-id="02f1b-194">Vídeo, [Cómo implementar una transformación Búsqueda en modo de memoria caché completa (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131031), en msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02f1b-194">Video, [How to: Implement a Lookup Transformation in Full Cache Mode](https://go.microsoft.com/fwlink/?LinkId=131031), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="02f1b-195">Entrada de blog, [Prácticas recomendadas para utilizar los modos de caché de la transformación Búsqueda](https://go.microsoft.com/fwlink/?LinkId=146623)(en inglés), en blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="02f1b-195">Blog entry, [Best Practices for Using the Lookup Transformation Cache Modes](https://go.microsoft.com/fwlink/?LinkId=146623), on blogs.msdn.com</span></span>  
  
-   <span data-ttu-id="02f1b-196">Entrada de blog, [Patrón de búsqueda: sin distinción de mayúsculas y minúsculas](https://go.microsoft.com/fwlink/?LinkId=157782), en blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="02f1b-196">Blog entry, [Lookup Pattern: Case Insensitive](https://go.microsoft.com/fwlink/?LinkId=157782), on blogs.msdn.com</span></span>  
  
-   <span data-ttu-id="02f1b-197">Ejemplo, [Transformación de búsqueda](https://go.microsoft.com/fwlink/?LinkId=267528), en msftisprodsamples.codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="02f1b-197">Sample, [Lookup Transformation](https://go.microsoft.com/fwlink/?LinkId=267528), on msftisprodsamples.codeplex.com.</span></span>  
  
     <span data-ttu-id="02f1b-198">Para obtener información acerca de cómo instalar muestras de producto y bases de datos de ejemplo de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , vea [Ejemplos del producto SQL Server Integration Services](https://go.microsoft.com/fwlink/?LinkId=267527).</span><span class="sxs-lookup"><span data-stu-id="02f1b-198">For information on installing [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] product samples and sample databases, see [SQL Server Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=267527).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02f1b-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02f1b-199">See Also</span></span>  
 <span data-ttu-id="02f1b-200">[Transformación búsqueda aproximada](fuzzy-lookup-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="02f1b-200">[Fuzzy Lookup Transformation](fuzzy-lookup-transformation.md) </span></span>  
 <span data-ttu-id="02f1b-201">[Transformación búsqueda de términos](term-lookup-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="02f1b-201">[Term Lookup Transformation](term-lookup-transformation.md) </span></span>  
 <span data-ttu-id="02f1b-202">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="02f1b-202">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="02f1b-203">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="02f1b-203">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  