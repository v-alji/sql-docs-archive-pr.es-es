---
title: Crear la función para recuperar los datos modificados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749407"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="00d5c-102">Crear la función para recuperar los datos modificados</span><span class="sxs-lookup"><span data-stu-id="00d5c-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="00d5c-103">Después de completar el flujo de control para un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de datos modificados, la tarea siguiente es crear una función con valores de tabla que recupere los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="00d5c-104">Solo tiene que crear esta función una vez antes de la primera carga incremental.</span><span class="sxs-lookup"><span data-stu-id="00d5c-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00d5c-105">La creación de una función para recuperar los datos modificados es el segundo paso en el proceso de crear un paquete que realiza una carga incremental de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="00d5c-106">Vea una descripción del proceso general para crear este paquete en [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="00d5c-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="00d5c-107">Consideraciones de diseño para las funciones de captura de datos modificados</span><span class="sxs-lookup"><span data-stu-id="00d5c-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="00d5c-108">Para recuperar los datos modificados, un componente de origen en el flujo de datos del paquete llama a una de las siguientes funciones de consulta de captura de datos modificados:</span><span class="sxs-lookup"><span data-stu-id="00d5c-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="00d5c-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** Para esta consulta, la única fila devuelta para cada actualización contiene el estado final de cada fila modificada.</span><span class="sxs-lookup"><span data-stu-id="00d5c-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="00d5c-110">En la mayoría de los casos, solo necesitará los datos devueltos por una consulta para los cambios netos.</span><span class="sxs-lookup"><span data-stu-id="00d5c-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="00d5c-111">Para obtener más información, vea [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="00d5c-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** Esta consulta devuelve todos los cambios que se han producido en cada fila durante el intervalo de captura.</span><span class="sxs-lookup"><span data-stu-id="00d5c-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="00d5c-113">Para obtener más información, vea [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="00d5c-114">A continuación, el componente de origen toma los resultados devueltos por la función y los pasa a las transformaciones y destinos de nivel inferior, que aplican los datos modificados al destino final.</span><span class="sxs-lookup"><span data-stu-id="00d5c-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="00d5c-115">Pero un componente de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no puede llamar directamente a estas funciones de captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="00d5c-116">Un componente de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] requiere metadatos sobre las columnas devueltas por la consulta.</span><span class="sxs-lookup"><span data-stu-id="00d5c-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="00d5c-117">Los funciones de captura de datos modificados no definen las columnas de su tabla de resultados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="00d5c-118">Así, estas funciones no devuelven metadatos suficientes para un componente de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00d5c-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="00d5c-119">Use una función de contenedor con valores de tabla, ya que este tipo de función define explícitamente las columnas de la tabla de resultados en su cláusula RETURNS.</span><span class="sxs-lookup"><span data-stu-id="00d5c-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="00d5c-120">Esta definición explícita de las columnas proporciona los metadatos que necesita un componente de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00d5c-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="00d5c-121">Debe crear esta función para cada tabla cuyos datos modificados desee recuperar.</span><span class="sxs-lookup"><span data-stu-id="00d5c-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="00d5c-122">Tiene dos opciones para crear la función de contenedor con valores de tabla que llama a la función de consulta de captura de datos modificados:</span><span class="sxs-lookup"><span data-stu-id="00d5c-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="00d5c-123">Puede llamar al procedimiento almacenado del sistema, **sys.sp_cdc_generate_wrapper_function** , que crea automáticamente funciones con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="00d5c-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="00d5c-124">Puede escribir su propia función con valores de tabla siguiendo las instrucciones y el ejemplo incluidos en este tema.</span><span class="sxs-lookup"><span data-stu-id="00d5c-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="00d5c-125">Llamar a un procedimiento almacenado para crear la función con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="00d5c-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="00d5c-126">La forma más rápida y sencilla de crear las funciones con valores de tabla que necesita es llamar al procedimiento almacenado del sistema, **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="00d5c-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="00d5c-127">Este procedimiento almacenado genera scripts para crear funciones de contenedor diseñadas específicamente para adaptarse a las necesidades de un componente de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00d5c-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="00d5c-128">El procedimiento almacenado del sistema **sys.sp_cdc_generate_wrapper_function** no crea directamente las funciones de contenedor.</span><span class="sxs-lookup"><span data-stu-id="00d5c-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="00d5c-129">Lo que hace es generar los scripts CREATE para las funciones de contenedor.</span><span class="sxs-lookup"><span data-stu-id="00d5c-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="00d5c-130">El desarrollador debe ejecutar los scripts CREATE generados por el procedimiento almacenado antes de que un paquete de carga incremental llame a las funciones de contenedor.</span><span class="sxs-lookup"><span data-stu-id="00d5c-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="00d5c-131">Para poder entender cómo se usa este procedimiento almacenado del sistema, debe comprender lo que hace, qué scripts genera y qué funciones de contenedor crean los scripts.</span><span class="sxs-lookup"><span data-stu-id="00d5c-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="00d5c-132">Entender y usar el procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="00d5c-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="00d5c-133">El procedimiento almacenado del sistema **sys.sp_cdc_generate_wrapper_function** genera los scripts necesarios para crear las funciones de contenedor que usarán los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00d5c-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="00d5c-134">Estas son las primeras líneas de la definición del procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="00d5c-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="00d5c-135">Todos los parámetros del procedimiento almacenado son opcionales.</span><span class="sxs-lookup"><span data-stu-id="00d5c-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="00d5c-136">Si llama al procedimiento almacenado sin haber proporcionado valores para alguno de los parámetros, dicho procedimiento creará funciones de contenedor para todas las instancias de captura a las que usted tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="00d5c-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00d5c-137">Para más información sobre la sintaxis de este procedimiento almacenado y sus parámetros, vea [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="00d5c-138">El procedimiento almacenado siempre genera una función de contenedor para devolver todos los cambios de cada instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="00d5c-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="00d5c-139">Si el *@supports_net_changes* parámetro se estableció cuando se creó la instancia de captura, el procedimiento almacenado también genera una función de contenedor para devolver los cambios netos de cada instancia de captura aplicable.</span><span class="sxs-lookup"><span data-stu-id="00d5c-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="00d5c-140">El procedimiento almacenado devuelve un conjunto de resultados con dos columnas:</span><span class="sxs-lookup"><span data-stu-id="00d5c-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="00d5c-141">El nombre de la función de contenedor generada por el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="00d5c-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="00d5c-142">Este procedimiento almacenado obtiene el nombre de la función a partir del nombre de la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="00d5c-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="00d5c-143">(El nombre de la función es 'fn_all_changes_' seguido por el nombre de la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="00d5c-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="00d5c-144">El prefijo usado para la función de cambios netos, si se crea, es 'fn_net_changes_'.)</span><span class="sxs-lookup"><span data-stu-id="00d5c-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="00d5c-145">La instrucción CREATE para la función de contenedor.</span><span class="sxs-lookup"><span data-stu-id="00d5c-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="00d5c-146">Entender y usar los scripts creados por el procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="00d5c-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="00d5c-147">Normalmente, un desarrollador usa una instrucción INSERT...EXEC para llamar al procedimiento almacenado **sys.sp_cdc_generate_wrapper_function** y guarda los scripts creados por ese procedimiento en una tabla temporal.</span><span class="sxs-lookup"><span data-stu-id="00d5c-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="00d5c-148">Una vez hecho esto, se podrá seleccionar y ejecutar cada script de manera individual para crear la función de contenedor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="00d5c-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="00d5c-149">Sin embargo, un desarrollador también puede usar un conjunto de comandos SQL para ejecutar todos los scripts CREATE, tal y como se muestra en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00d5c-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="00d5c-150">Entender y usar las funciones creadas por el procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="00d5c-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="00d5c-151">Para recorrer de forma sistemática la escala de tiempo de los datos modificados capturados, las funciones de contenedor generadas esperan que el *@end_time* parámetro de un intervalo sea el *@start_time* parámetro para el intervalo subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="00d5c-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="00d5c-152">Cuando se sigue esta convención, las funciones de contenedor generadas pueden realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="00d5c-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="00d5c-153">Asignar los valores de fecha y hora a los valores LSN que se usan internamente.</span><span class="sxs-lookup"><span data-stu-id="00d5c-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="00d5c-154">Asegurarse de que no se pierde ni se repite ningún dato.</span><span class="sxs-lookup"><span data-stu-id="00d5c-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="00d5c-155">Para simplificar las consultas de todas las filas de una tabla de cambios, las funciones de contenedor generadas también admiten las convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="00d5c-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="00d5c-156">Si el parámetro @start_time es NULL, las funciones de contenedor usan el valor LSN más bajo de la instancia de captura como el límite inferior de la consulta.</span><span class="sxs-lookup"><span data-stu-id="00d5c-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="00d5c-157">Si el parámetro @end_time es NULL, las funciones de contenedor usan el valor LSN más alto de la instancia de captura como el límite superior de la consulta.</span><span class="sxs-lookup"><span data-stu-id="00d5c-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="00d5c-158">La mayoría de los usuarios podrán usar las funciones de contenedor creadas por el procedimiento almacenado del sistema, **sys.sp_cdc_generate_wrapper_function** , sin realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="00d5c-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="00d5c-159">Sin embargo, para personalizar las funciones de contenedor, es necesario personalizar los scripts CREATE antes de ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="00d5c-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="00d5c-160">Cuando el paquete llame a las funciones de contenedor, el paquete debe proporcionar valores para tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="00d5c-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="00d5c-161">Estos tres parámetros son como los tres parámetros que usan las funciones de captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="00d5c-162">Los tres parámetros son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="00d5c-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="00d5c-163">Valor de fecha y hora de inicio, y valor de fecha y hora de finalización del intervalo.</span><span class="sxs-lookup"><span data-stu-id="00d5c-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="00d5c-164">Aunque las funciones de contenedor usan valores de fecha y hora como los puntos inicial y final del intervalo de consulta, las funciones de captura de datos modificados usan dos valores LSN como dichos puntos.</span><span class="sxs-lookup"><span data-stu-id="00d5c-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="00d5c-165">El filtro de filas.</span><span class="sxs-lookup"><span data-stu-id="00d5c-165">The row filter.</span></span> <span data-ttu-id="00d5c-166">Para las funciones de contenedor y las funciones de captura de datos modificados, el *@row_filter_option* parámetro es el mismo.</span><span class="sxs-lookup"><span data-stu-id="00d5c-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="00d5c-167">Para más información, vea [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) y [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="00d5c-168">El conjunto de resultados devuelto por las funciones de contenedor incluye los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="00d5c-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="00d5c-169">Todas las columnas de datos modificados solicitadas.</span><span class="sxs-lookup"><span data-stu-id="00d5c-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="00d5c-170">Una columna denominada __CDC_OPERATION que usa un campo de uno o dos caracteres para identificar la operación que está asociada a la fila.</span><span class="sxs-lookup"><span data-stu-id="00d5c-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="00d5c-171">Los valores válidos para este campo son los siguientes: "I" para insertar, "D" para eliminar, "UO" para actualizar valores antiguos y "UN" para actualizar valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="00d5c-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="00d5c-172">Marcas de actualización, cuando se solicitan, que aparecen como columnas de bits después del código de operación y en el orden especificado en el *@update_flag_list* parámetro.</span><span class="sxs-lookup"><span data-stu-id="00d5c-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="00d5c-173">El nombre de estas columnas se obtiene anexando “_uflag” al nombre de columna asociado.</span><span class="sxs-lookup"><span data-stu-id="00d5c-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="00d5c-174">Si el paquete llama a una función de contenedor que consulta todos los cambios, dicha función también devolverá las columnas __CDC_STARTLSN y \__CDC_SEQVAL.</span><span class="sxs-lookup"><span data-stu-id="00d5c-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="00d5c-175">Estas dos columnas se convierten en la primera y en la segunda columna, respectivamente, del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="00d5c-176">La función de contenedor también ordena el conjunto de resultados basándose en estas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="00d5c-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="00d5c-177">Escribir su propia función con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="00d5c-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="00d5c-178">También puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para escribir su propia función de contenedor con valores de tabla que llame a la función de consulta de captura de datos modificados y almacenar la función de contenedor con valores de tabla en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00d5c-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00d5c-179">Para más información sobre cómo crear una función Transact-SQL, vea [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="00d5c-180">En el ejemplo siguiente se define una función con valores de tabla que recupera los cambios de una tabla Customer para el intervalo de cambios especificado.</span><span class="sxs-lookup"><span data-stu-id="00d5c-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="00d5c-181">Esta función utiliza las funciones de captura de datos modificados para asignar los valores `datetime` a los valores de número de flujo de registro binario (LSN) que las tablas de cambios utilizan internamente.</span><span class="sxs-lookup"><span data-stu-id="00d5c-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="00d5c-182">Esta función también controla varias condiciones especiales:</span><span class="sxs-lookup"><span data-stu-id="00d5c-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="00d5c-183">Cuando se pasa un valor nulo para la fecha y hora de inicio, esta función utiliza el primer valor disponible.</span><span class="sxs-lookup"><span data-stu-id="00d5c-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="00d5c-184">Cuando se pasa un valor nulo para la fecha y hora de finalización, esta función utiliza el último valor disponible.</span><span class="sxs-lookup"><span data-stu-id="00d5c-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="00d5c-185">Cuando el LSN inicial es igual que el LSN final, lo que suele implicar que no hay ningún registro para el intervalo seleccionado, esta función finaliza.</span><span class="sxs-lookup"><span data-stu-id="00d5c-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="00d5c-186">Ejemplo de una función con valores de tabla que consulta los datos modificados</span><span class="sxs-lookup"><span data-stu-id="00d5c-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="00d5c-187">Recuperar metadatos adicionales con los datos modificados</span><span class="sxs-lookup"><span data-stu-id="00d5c-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="00d5c-188">Aunque la función con valores de tabla creada por el usuario y mostrada anteriormente solo usa la columna **__$operation**, la función **cdc.fn_cdc_get_net_changes_<capture_instance>** devuelve cuatro columnas de metadatos por cada fila de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="00d5c-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="00d5c-189">Si desea utilizar estos valores en el flujo de datos, puede devolverlos como columnas adicionales desde la función contenedora con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="00d5c-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="00d5c-190">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="00d5c-190">Column name</span></span>|<span data-ttu-id="00d5c-191">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="00d5c-191">Data type</span></span>|<span data-ttu-id="00d5c-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="00d5c-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="00d5c-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="00d5c-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="00d5c-194">Número de secuencia de registro (LSN) asociado con la transacción de confirmación para el cambio.</span><span class="sxs-lookup"><span data-stu-id="00d5c-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="00d5c-195">Todos los cambios confirmados en la misma transacción comparten el mismo LSN de confirmación.</span><span class="sxs-lookup"><span data-stu-id="00d5c-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="00d5c-196">Por ejemplo, si una operación de actualización en la tabla de origen modifica dos filas diferentes, la tabla de cambios contendrá cuatro filas (dos con los valores anteriores y dos con los valores nuevos), cada una con el mismo valor **__$start_lsn** .</span><span class="sxs-lookup"><span data-stu-id="00d5c-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="00d5c-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="00d5c-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="00d5c-198">Valor de secuencia que se usa para ordenar los cambios de fila en una transacción.</span><span class="sxs-lookup"><span data-stu-id="00d5c-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="00d5c-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="00d5c-199">**__$operation**</span></span>|`int`|<span data-ttu-id="00d5c-200">Operación del lenguaje de manipulación de datos (DML) asociada al cambio.</span><span class="sxs-lookup"><span data-stu-id="00d5c-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="00d5c-201">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="00d5c-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="00d5c-202">1 = eliminar</span><span class="sxs-lookup"><span data-stu-id="00d5c-202">1 = delete</span></span><br /><br /> <span data-ttu-id="00d5c-203">2 = insertar</span><span class="sxs-lookup"><span data-stu-id="00d5c-203">2 = insert</span></span><br /><br /> <span data-ttu-id="00d5c-204">3 = actualizar (valores antes de la operación de actualización)</span><span class="sxs-lookup"><span data-stu-id="00d5c-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="00d5c-205">4 = actualizar (valores después de la operación de actualización)</span><span class="sxs-lookup"><span data-stu-id="00d5c-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="00d5c-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="00d5c-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="00d5c-207">Máscara de bits basada en los ordinales de las columnas de la tabla de cambios que identifica las columnas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="00d5c-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="00d5c-208">Puede examinar este valor para determinar las columnas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="00d5c-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="00d5c-209">Varía</span><span class="sxs-lookup"><span data-stu-id="00d5c-209">varies</span></span>|<span data-ttu-id="00d5c-210">Las columnas restantes devueltas por la función son las columnas de la tabla de origen que se identificaron como columnas capturadas cuando se creó la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="00d5c-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="00d5c-211">Si no se especificó inicialmente ninguna columna en la lista de columnas capturadas, se devuelven todas las columnas de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="00d5c-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="00d5c-212">Para obtener más información, vea [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00d5c-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="00d5c-213">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="00d5c-213">Next Step</span></span>  
 <span data-ttu-id="00d5c-214">Una vez que haya creado la función con valores de tabla que consulta los datos modificados, el paso siguiente consiste en comenzar a diseñar el flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="00d5c-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="00d5c-215">**Tema siguiente:** [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="00d5c-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
