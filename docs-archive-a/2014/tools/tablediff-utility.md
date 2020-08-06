---
title: Utilidad tablediff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747812"
---
# <a name="tablediff-utility"></a><span data-ttu-id="4f712-102">tablediff, utilidad</span><span class="sxs-lookup"><span data-stu-id="4f712-102">tablediff Utility</span></span>
  <span data-ttu-id="4f712-103">La utilidad **tablediff** se usa para comparar los datos de dos tablas para determinar la no convergencia y es especialmente útil para solucionar problemas de no convergencia en una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="4f712-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="4f712-104">Esta utilidad se puede usar desde el símbolo del sistema o en un archivo por lotes para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4f712-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4f712-105">Una comparación fila a fila entre una tabla de origen de una instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que actúa como publicador de replicación y la tabla de destino de una o más instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que actúan como suscriptores de replicación.</span><span class="sxs-lookup"><span data-stu-id="4f712-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="4f712-106">Realiza una comparación rápida comparando solo el número de filas y el esquema.</span><span class="sxs-lookup"><span data-stu-id="4f712-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="4f712-107">Realizar comparaciones de nivel de columna.</span><span class="sxs-lookup"><span data-stu-id="4f712-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="4f712-108">Generar un script [!INCLUDE[tsql](../includes/tsql-md.md)] para solucionar discrepancias en el servidor de destino y hacer que las tablas de destino y de origen converjan.</span><span class="sxs-lookup"><span data-stu-id="4f712-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="4f712-109">Registrar resultados en un archivo de salida o en una tabla de la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f712-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f712-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f712-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4f712-111">Arguments</span></span>  
 <span data-ttu-id="4f712-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="4f712-112">[ **-?**</span></span> <span data-ttu-id="4f712-113">]</span><span class="sxs-lookup"><span data-stu-id="4f712-113">]</span></span>  
 <span data-ttu-id="4f712-114">Devuelve la lista de parámetros admitidos.</span><span class="sxs-lookup"><span data-stu-id="4f712-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="4f712-115">**-sourceserver** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="4f712-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="4f712-116">Es el nombre del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="4f712-116">Is the name of the source server.</span></span> <span data-ttu-id="4f712-117">Especifique _el \_ \_ nombre del servidor de origen_ para la instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f712-118">Especifique _ \_ \_ _ **\\** _ \_ el nombre de instancia_ del servidor de origen para una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4f712-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="4f712-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="4f712-120">Es el nombre de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="4f712-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="4f712-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="4f712-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="4f712-122">Es el nombre de la tabla de origen que se está comprobando.</span><span class="sxs-lookup"><span data-stu-id="4f712-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="4f712-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="4f712-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="4f712-124">Es el propietario del esquema de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="4f712-124">The schema owner of the source table.</span></span> <span data-ttu-id="4f712-125">De forma predeterminada, se asume que el propietario de la tabla es dbo.</span><span class="sxs-lookup"><span data-stu-id="4f712-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="4f712-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="4f712-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="4f712-127">Es la contraseña para el inicio de sesión que se usa para conectar con el servidor de origen mediante autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f712-128">Cuando sea posible, proporcione credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f712-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="4f712-129">Si debe almacenar credenciales en un archivo de script, debe proteger el archivo para impedir el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="4f712-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="4f712-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="4f712-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="4f712-131">Es el inicio de sesión que se usa para conectar con el servidor de origen mediante autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4f712-132">Si no se proporciona *source_login* , se usa autenticación de Windows para conectar con el servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="4f712-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="4f712-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="4f712-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="4f712-134">La tabla de origen se bloquea durante la comparación con las sugerencias de tabla TABLOCK y HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="4f712-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="4f712-135">**-destinationserver** *destination_server_name*[ **\\** _ \_ nombre de instancia_]</span><span class="sxs-lookup"><span data-stu-id="4f712-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="4f712-136">Es el nombre del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-136">Is the name of the destination server.</span></span> <span data-ttu-id="4f712-137">Especifique *destination_server_name* para la instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f712-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f712-138">Especifique _ \_ \_ _ **\\** _ \_ el nombre de instancia_ del servidor de destino para una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4f712-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="4f712-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="4f712-140">Es el nombre de la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="4f712-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="4f712-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="4f712-142">Es el nombre de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="4f712-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="4f712-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="4f712-144">Es el propietario del esquema de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-144">The schema owner of the destination table.</span></span> <span data-ttu-id="4f712-145">De forma predeterminada, se asume que el propietario de la tabla es dbo.</span><span class="sxs-lookup"><span data-stu-id="4f712-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="4f712-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="4f712-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="4f712-147">Es la contraseña para el inicio de sesión que se usa para conectar con el servidor de destino mediante autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f712-148">Cuando sea posible, proporcione credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f712-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="4f712-149">Si debe almacenar credenciales en un archivo de script, debe proteger el archivo para impedir el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="4f712-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="4f712-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="4f712-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="4f712-151">Es el inicio de sesión que se usa para conectar con el servidor de destino mediante autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4f712-152">Si no se proporciona *destination_login* , se usa autenticación de Windows para conectar con el servidor.</span><span class="sxs-lookup"><span data-stu-id="4f712-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="4f712-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="4f712-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="4f712-154">La tabla de destino se bloquea durante la comparación con las sugerencias de tabla TABLOCK y HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="4f712-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="4f712-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="4f712-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="4f712-156">Es el número de bytes que se deben comparar en las columnas cuyo tipo de datos es de objetos grandes, lo que incluye los tipos: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` y `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="4f712-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="4f712-157">*large_object_bytes* toma como valor predeterminado el tamaño de la columna.</span><span class="sxs-lookup"><span data-stu-id="4f712-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="4f712-158">Los datos que superen *large_object_bytes* no se compararán.</span><span class="sxs-lookup"><span data-stu-id="4f712-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="4f712-159">**-bf**  *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="4f712-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="4f712-160">Es el número de instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] que se va a escribir en el archivo de script actual [!INCLUDE[tsql](../includes/tsql-md.md)] cuando se usa la opción **-f** .</span><span class="sxs-lookup"><span data-stu-id="4f712-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="4f712-161">Cuando el número de instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] supera el valor de *number_of_statements*, se crea un nuevo archivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="4f712-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="4f712-162">**-c**</span></span>  
 <span data-ttu-id="4f712-163">Compara diferencias de nivel de columna.</span><span class="sxs-lookup"><span data-stu-id="4f712-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="4f712-164">**-dt**</span><span class="sxs-lookup"><span data-stu-id="4f712-164">**-dt**</span></span>  
 <span data-ttu-id="4f712-165">Quita la tabla de resultados especificada por *table_name*si la tabla ya existe.</span><span class="sxs-lookup"><span data-stu-id="4f712-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="4f712-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="4f712-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="4f712-167">Especifica el nombre de la tabla de resultados que se desea crear.</span><span class="sxs-lookup"><span data-stu-id="4f712-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="4f712-168">Si ya existe esta tabla, debe usarse **-DT** o la operación no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f712-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="4f712-169">**-f** [ *file_name* ]</span><span class="sxs-lookup"><span data-stu-id="4f712-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="4f712-170">Genera un script de [!INCLUDE[tsql](../includes/tsql-md.md)] para hacer que la tabla del servidor de destino converja con la tabla del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="4f712-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="4f712-171">Tiene la opción de especificar un nombre y una ruta de acceso para el archivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] generado.</span><span class="sxs-lookup"><span data-stu-id="4f712-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="4f712-172">Si no se especifica *file_name* , el archivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] se genera en el directorio en el que se ejecuta la utilidad.</span><span class="sxs-lookup"><span data-stu-id="4f712-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="4f712-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="4f712-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="4f712-174">Es la ruta y el nombre completo del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="4f712-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="4f712-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="4f712-175">**-q**</span></span>  
 <span data-ttu-id="4f712-176">Realiza una comparación rápida comparando solo el número de filas y el esquema.</span><span class="sxs-lookup"><span data-stu-id="4f712-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="4f712-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="4f712-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="4f712-178">Número de reintentos de la utilidad para operaciones con errores.</span><span class="sxs-lookup"><span data-stu-id="4f712-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="4f712-179">**-ri**  *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="4f712-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="4f712-180">Intervalo (en segundos) entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="4f712-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="4f712-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="4f712-181">**-strict**</span></span>  
 <span data-ttu-id="4f712-182">El esquema de origen y de destino se comparan de forma estricta.</span><span class="sxs-lookup"><span data-stu-id="4f712-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="4f712-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="4f712-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="4f712-184">Establece el período de tiempo de espera de la conexión, en segundos, para las conexiones con el servidor de origen y el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f712-185">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f712-185">Return Value</span></span>  
  
|<span data-ttu-id="4f712-186">Value</span><span class="sxs-lookup"><span data-stu-id="4f712-186">Value</span></span>|<span data-ttu-id="4f712-187">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f712-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f712-188">**0**</span><span class="sxs-lookup"><span data-stu-id="4f712-188">**0**</span></span>|<span data-ttu-id="4f712-189">Correcto</span><span class="sxs-lookup"><span data-stu-id="4f712-189">Success</span></span>|  
|<span data-ttu-id="4f712-190">**1**</span><span class="sxs-lookup"><span data-stu-id="4f712-190">**1**</span></span>|<span data-ttu-id="4f712-191">Error grave</span><span class="sxs-lookup"><span data-stu-id="4f712-191">Critical error</span></span>|  
|<span data-ttu-id="4f712-192">**2**</span><span class="sxs-lookup"><span data-stu-id="4f712-192">**2**</span></span>|<span data-ttu-id="4f712-193">Diferencias entre tablas</span><span class="sxs-lookup"><span data-stu-id="4f712-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f712-194">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f712-194">Remarks</span></span>  
 <span data-ttu-id="4f712-195">La utilidad **tablediff** no se puede usar con servidores que no sean de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f712-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="4f712-196">No se admiten tablas que contengan columnas con el tipo de datos `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="4f712-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="4f712-197">De forma predeterminada, la utilidad **tablediff** admite las siguientes asignaciones de tipos de datos entre las columnas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="4f712-198">Tipo de datos de origen</span><span class="sxs-lookup"><span data-stu-id="4f712-198">Source data type</span></span>|<span data-ttu-id="4f712-199">Tipo de datos de destino</span><span class="sxs-lookup"><span data-stu-id="4f712-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="4f712-200">`smallint`, `int` o `bigint`</span><span class="sxs-lookup"><span data-stu-id="4f712-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="4f712-201">`int` o `bigint`</span><span class="sxs-lookup"><span data-stu-id="4f712-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="4f712-202">Use la opción **-strict** para no permitir estas asignaciones y llevar a cabo una validación estricta.</span><span class="sxs-lookup"><span data-stu-id="4f712-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="4f712-203">La tabla de origen de la comparación debe contener como mínimo una columna de clave principal, de identidad o ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="4f712-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="4f712-204">Cuando se emplea la opción **-strict** , la tabla de destino también debe tener una columna de clave principal, de identidad o ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="4f712-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="4f712-205">El script [!INCLUDE[tsql](../includes/tsql-md.md)] generado para hacer que la tabla de destino converja no incluye los siguientes tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="4f712-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="4f712-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="4f712-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="4f712-207">Permisos</span><span class="sxs-lookup"><span data-stu-id="4f712-207">Permissions</span></span>  
 <span data-ttu-id="4f712-208">Para comparar tablas, necesita los permisos SELECT ALL en los objetos de la tabla que se están comparando.</span><span class="sxs-lookup"><span data-stu-id="4f712-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="4f712-209">Para usar la opción **-et** , debe ser miembro del rol fijo de base de datos db_owner o, como mínimo, tener el permiso CREATE TABLE en la base de datos de suscripciones y el permiso ALTER en el esquema del propietario de destino del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="4f712-210">Para usar la opción **-dt** , debe ser miembro del rol fijo de base de datos db_owner o, como mínimo, tener el permiso ALTER en el esquema del propietario de destino del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4f712-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="4f712-211">Para usar las opciones **-o** o **-f** , debe tener permisos de escritura en la ubicación del directorio de archivos especificada.</span><span class="sxs-lookup"><span data-stu-id="4f712-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f712-212">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f712-212">See Also</span></span>  
 [<span data-ttu-id="4f712-213">Comparar tablas replicadas para buscar diferencias &#40;programación de la replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="4f712-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
