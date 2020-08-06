---
title: Determinar si los datos modificados están preparados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749401"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="28867-102">Determinar si los datos modificados están preparados</span><span class="sxs-lookup"><span data-stu-id="28867-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="28867-103">En el flujo de control de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de los datos modificados, la segunda tarea consiste en asegurarse de que éstos están listos para el intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="28867-104">Este paso es necesario porque el proceso de captura asincrónico podría no haber procesado todavía todos los cambios hasta el extremo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28867-105">La primera tarea para el flujo de control consiste en calcular los extremos del intervalo de cambios.</span><span class="sxs-lookup"><span data-stu-id="28867-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="28867-106">Para más información sobre esta tarea, vea [Especificar un intervalo de datos modificados](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="28867-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="28867-107">Para obtener una descripción del proceso general de diseño del flujo de control, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="28867-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="28867-108">Entender los componentes de la solución</span><span class="sxs-lookup"><span data-stu-id="28867-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="28867-109">La solución descrita en este tema usa 4 componentes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="28867-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="28867-110">Un contenedor de bucles For que evalúa repetidamente la salida de una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="28867-111">Una tarea Ejecutar SQL que consulta tablas especiales mantenidas por el proceso de captura de datos modificados y, a continuación, utiliza esta información para determinar si éstos están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="28867-112">Un componente que implementa un retraso en el procesamiento cuando los datos no están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="28867-113">Puede ser una tarea Script o una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="28867-114">Opcionalmente, un componente que informa de un error o de que se ha superado el tiempo de espera cuando la tarea Ejecutar SQL devuelve un valor que indica una de esas condiciones.</span><span class="sxs-lookup"><span data-stu-id="28867-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="28867-115">Estos componentes establecen o leen los valores de varias variables del paquete para controlar el flujo de ejecución dentro del bucle y después en el paquete.</span><span class="sxs-lookup"><span data-stu-id="28867-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="28867-116">Para establecer las variables de paquetes</span><span class="sxs-lookup"><span data-stu-id="28867-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="28867-117">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la ventana **Variables** , cree las variables siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="28867-118">Cree una variable con un tipo de datos entero para almacenar el valor de estado devuelto por la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="28867-119">En este ejemplo se utiliza el nombre de variable DataReady con un valor inicial de 0.</span><span class="sxs-lookup"><span data-stu-id="28867-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="28867-120">Cree una variable para almacenar el período de tiempo de retraso cuando los datos no están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="28867-121">Si desea utilizar una tarea Script para implementar el retraso, la variable debería tener un tipo de datos entero.</span><span class="sxs-lookup"><span data-stu-id="28867-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="28867-122">Si desea utilizar una tarea Ejecutar SQL con una instrucción WAITFOR, la variable debería tener un tipo de datos de cadena para aceptar valores como "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="28867-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="28867-123">En este ejemplo se utiliza el nombre de variable DelaySeconds con un valor inicial de 10.</span><span class="sxs-lookup"><span data-stu-id="28867-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="28867-124">Cree una variable con un tipo de datos entero para almacenar la iteración actual del bucle.</span><span class="sxs-lookup"><span data-stu-id="28867-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="28867-125">En este ejemplo se utiliza el nombre de variable TimeoutCount con un valor inicial de 0.</span><span class="sxs-lookup"><span data-stu-id="28867-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="28867-126">Cree una variable con un tipo de datos entero para especificar el número de veces que el bucle debería comprobar la existencia de datos antes de informar de un error de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="28867-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="28867-127">En este ejemplo se utiliza el nombre de variable TimeoutCeiling con un valor inicial de 20.</span><span class="sxs-lookup"><span data-stu-id="28867-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="28867-128">(Opcional) Cree una variable con un tipo de datos entero que podrá utilizar para indicar la primera carga de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="28867-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="28867-129">En este ejemplo se utiliza el nombre de variable IntervalID y solamente se comprueba que exista un valor de 0 que indique la carga inicial.</span><span class="sxs-lookup"><span data-stu-id="28867-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="28867-130">Configurar un contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="28867-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="28867-131">Con las variables establecidas, el contenedor de bucles For es el primer componente que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="28867-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="28867-132">Para configurar un contenedor de bucles For de tal forma que espere hasta que los datos modificados estén listos</span><span class="sxs-lookup"><span data-stu-id="28867-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="28867-133">En la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue un contenedor de bucles For al flujo de control.</span><span class="sxs-lookup"><span data-stu-id="28867-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="28867-134">Conecte la tarea Ejecutar SQL que calcula los extremos del intervalo al contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="28867-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="28867-135">En el **Editor de bucles For**, seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-136">Para **InitExpression**, escriba `@DataReady = 0`.</span><span class="sxs-lookup"><span data-stu-id="28867-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="28867-137">Esta expresión establece el valor inicial de la variable de bucle.</span><span class="sxs-lookup"><span data-stu-id="28867-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="28867-138">Para **EvalExpression**, escriba `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="28867-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="28867-139">Cuando esta expresión se evalúa como **False**, la ejecución se transfiere al bucle y comienza la carga incremental.</span><span class="sxs-lookup"><span data-stu-id="28867-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="28867-140">Configurar la tarea Ejecutar SQL que consulta los datos modificados</span><span class="sxs-lookup"><span data-stu-id="28867-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="28867-141">Dentro del contenedor de bucles For, agregue una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="28867-142">Esta tarea consulta las tablas que el proceso de captura de datos modificados mantiene en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28867-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="28867-143">El resultado de esta consulta es un valor de estado que indica si los datos modificados están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="28867-144">En la tabla siguiente, la primera columna muestra los valores devueltos desde la tarea Ejecutar SQL por la consulta de ejemplo de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="28867-145">La segunda columna muestra cómo responden los otros componentes a estos valores.</span><span class="sxs-lookup"><span data-stu-id="28867-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="28867-146">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28867-146">Return Value</span></span>|<span data-ttu-id="28867-147">Significado</span><span class="sxs-lookup"><span data-stu-id="28867-147">Meaning</span></span>|<span data-ttu-id="28867-148">Response</span><span class="sxs-lookup"><span data-stu-id="28867-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="28867-149">0</span><span class="sxs-lookup"><span data-stu-id="28867-149">0</span></span>|<span data-ttu-id="28867-150">Indica que los datos modificados no están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="28867-151">No hay ningún registro de captura de datos modificados posterior al punto final del intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="28867-152">La ejecución continúa con el componente que implementa un retraso.</span><span class="sxs-lookup"><span data-stu-id="28867-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="28867-153">A continuación, el control vuelve al contenedor de bucles For, que sigue comprobando la tarea Ejecutar SQL mientras el valor devuelto sea 0.</span><span class="sxs-lookup"><span data-stu-id="28867-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="28867-154">1</span><span class="sxs-lookup"><span data-stu-id="28867-154">1</span></span>|<span data-ttu-id="28867-155">Podría indicar que no se han capturado los datos modificados para el intervalo completo, o que se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="28867-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="28867-156">Esto se trata como una condición de error.</span><span class="sxs-lookup"><span data-stu-id="28867-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="28867-157">No hay ningún registro de captura de datos modificados anterior al punto inicial del intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="28867-158">La ejecución continúa con el componente opcional que registra el error.</span><span class="sxs-lookup"><span data-stu-id="28867-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="28867-159">2</span><span class="sxs-lookup"><span data-stu-id="28867-159">2</span></span>|<span data-ttu-id="28867-160">Indica que los datos están listos.</span><span class="sxs-lookup"><span data-stu-id="28867-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="28867-161">Hay registros de captura de datos modificados anteriores al punto inicial y posteriores al punto final del intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="28867-162">La ejecución se transfiere al contenedor de bucles For y comienza la carga incremental.</span><span class="sxs-lookup"><span data-stu-id="28867-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="28867-163">3</span><span class="sxs-lookup"><span data-stu-id="28867-163">3</span></span>|<span data-ttu-id="28867-164">Indica la carga inicial de todos los datos modificados disponibles.</span><span class="sxs-lookup"><span data-stu-id="28867-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="28867-165">La lógica condicional obtiene este valor de una variable de paquete especial que solamente se utiliza para este propósito.</span><span class="sxs-lookup"><span data-stu-id="28867-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="28867-166">La ejecución se transfiere al contenedor de bucles For y comienza la carga incremental.</span><span class="sxs-lookup"><span data-stu-id="28867-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="28867-167">5</span><span class="sxs-lookup"><span data-stu-id="28867-167">5</span></span>|<span data-ttu-id="28867-168">Indica que se ha alcanzado el valor de la variable TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="28867-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="28867-169">El bucle ha comprobado la existencia de datos el número de veces especificado, pero los datos todavía no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="28867-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="28867-170">Sin esta prueba u otra similar, el paquete podría ejecutarse indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="28867-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="28867-171">La ejecución continúa con el componente opcional que registra el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="28867-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="28867-172">Para configurar una tarea Ejecutar SQL de forma que consulte si los datos modificados están listos</span><span class="sxs-lookup"><span data-stu-id="28867-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="28867-173">Dentro del contenedor de bucles For, agregue una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="28867-174">En el **Editor de la tarea Ejecutar SQL**, en la página **General** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-175">En **Conjunto de resultados**, seleccione **Fila única**.</span><span class="sxs-lookup"><span data-stu-id="28867-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="28867-176">Configure una conexión válida con una base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="28867-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="28867-177">En **SQLSourceType**, seleccione **Entrada directa**.</span><span class="sxs-lookup"><span data-stu-id="28867-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="28867-178">En **SQLStatement**, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="28867-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="28867-179">En la página **Asignación de parámetros** del **Editor de la tarea Ejecutar SQL**, realice las asignaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="28867-180">Asigne la variable ExtractEndTime al parámetro 0.</span><span class="sxs-lookup"><span data-stu-id="28867-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="28867-181">Asigne la variable IntervalID al parámetro 1.</span><span class="sxs-lookup"><span data-stu-id="28867-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="28867-182">Asigne la variable ExtractStartTime al parámetro 2.</span><span class="sxs-lookup"><span data-stu-id="28867-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="28867-183">Asigne la variable TimeoutCount al parámetro 3.</span><span class="sxs-lookup"><span data-stu-id="28867-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="28867-184">Asigne la variable TimeoutCeiling al parámetro 4.</span><span class="sxs-lookup"><span data-stu-id="28867-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="28867-185">En la página **Conjunto de resultados** del **Editor de la tarea Ejecutar SQL**, asigne el resultado de DataReady a la variable DataReady, y el resultado de TimeoutCount a la variable TimeoutCount.</span><span class="sxs-lookup"><span data-stu-id="28867-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="28867-186">Esperar hasta que los datos modificados estén listos</span><span class="sxs-lookup"><span data-stu-id="28867-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="28867-187">Puede utilizar varios métodos para implementar un retraso cuando los datos modificados no estén listos.</span><span class="sxs-lookup"><span data-stu-id="28867-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="28867-188">Los dos procedimientos siguientes muestran cómo utilizar una tarea Script o una tarea Ejecutar SQL para implementar el retraso.</span><span class="sxs-lookup"><span data-stu-id="28867-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28867-189">Un script precompilado produce menos sobrecarga que una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="28867-190">Para implementar un retraso mediante una tarea Script</span><span class="sxs-lookup"><span data-stu-id="28867-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="28867-191">Dentro del contenedor de bucles For, agregue una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="28867-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="28867-192">Conecte a la nueva tarea Script la tarea Ejecutar SQL que hace la consulta para determinar si los datos modificados están preparados.</span><span class="sxs-lookup"><span data-stu-id="28867-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="28867-193">Para obtener la restricción de precedencia que conecta la tarea Ejecutar SQL a la tarea Script, abra el **Editor de restricciones de precedencia** y seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-194">En **Operación de evaluación**, seleccione **Expresión y restricción**.</span><span class="sxs-lookup"><span data-stu-id="28867-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="28867-195">En **Valor**, seleccione **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="28867-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="28867-196">El valor de restricción **Correcto** se refiere a la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="28867-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="28867-197">En este caso, la tarea Ejecutar SQL debe haberse realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="28867-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="28867-198">Para **Expresión**, escriba `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span><span class="sxs-lookup"><span data-stu-id="28867-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="28867-199">Seleccione **AND lógico. Todas las restricciones deben evaluarse como True**, si no está ya seleccionada.</span><span class="sxs-lookup"><span data-stu-id="28867-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="28867-200">En el **Editor de la tarea Script**, en la página **Script** , para **ReadOnlyVariables**, seleccione la variable de entero **User::DelaySeconds** en la lista.</span><span class="sxs-lookup"><span data-stu-id="28867-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="28867-201">En el **Editor de la tarea Script**, en la página **Script** , haga clic en **Modificar script** para abrir el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="28867-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="28867-202">En el procedimiento Main, escriba una de las líneas de código siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="28867-203">Si está programando en C#, escriba la línea de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="28867-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="28867-204">\- O bien</span><span class="sxs-lookup"><span data-stu-id="28867-204">\- or -</span></span>  
  
    -   <span data-ttu-id="28867-205">Si está programando en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], escriba la línea de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="28867-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="28867-206">El método `Thread.Sleep` espera un argumento especificado en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="28867-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="28867-207">Deje la línea de código predeterminada que devuelve `DtsExecResult.Success` de la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="28867-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="28867-208">Cierre el entorno de desarrollo de script y el **Editor de la tarea Script**.</span><span class="sxs-lookup"><span data-stu-id="28867-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="28867-209">Para implementar un retraso mediante una tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="28867-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="28867-210">Dentro del contenedor de bucles For, agregue una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="28867-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="28867-211">Conecte a la nueva tarea Ejecutar SQL la tarea Ejecutar SQL que hace la consulta para determinar si los datos modificados están preparados.</span><span class="sxs-lookup"><span data-stu-id="28867-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="28867-212">Para obtener la restricción de precedencia que conecta las dos tareas Ejecutar SQL, abra el **Editor de restricciones de precedencia** y seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-213">En **Operación de evaluación**, seleccione **Expresión y restricción**.</span><span class="sxs-lookup"><span data-stu-id="28867-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="28867-214">En **Valor**, seleccione **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="28867-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="28867-215">El valor de restricción **Correcto** se refiere a la tarea Ejecutar SQL anterior.</span><span class="sxs-lookup"><span data-stu-id="28867-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="28867-216">Para **Expresión**, escriba `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="28867-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="28867-217">Seleccione **AND lógico. Todas las restricciones deben evaluarse como True**, si no está ya seleccionada.</span><span class="sxs-lookup"><span data-stu-id="28867-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="28867-218">Esta selección requiere que ambas condiciones, la restricción y la expresión, sean true.</span><span class="sxs-lookup"><span data-stu-id="28867-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="28867-219">En el **Editor de la tarea Ejecutar SQL**, en la página **General** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-220">En **Conjunto de resultados**, seleccione **Fila única**.</span><span class="sxs-lookup"><span data-stu-id="28867-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="28867-221">Configure una conexión válida con una base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="28867-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="28867-222">En **SQLSourceType**, seleccione **Entrada directa**.</span><span class="sxs-lookup"><span data-stu-id="28867-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="28867-223">En **SQLStatement**, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="28867-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="28867-224">En la página **Asignación de parámetros** del editor, asigne la variable de cadena DelaySeconds al parámetro 0.</span><span class="sxs-lookup"><span data-stu-id="28867-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="28867-225">Controlar una condición de error</span><span class="sxs-lookup"><span data-stu-id="28867-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="28867-226">Si lo desea, puede configurar un componente adicional dentro del bucle para registrar un error o que se ha superado el tiempo de espera:</span><span class="sxs-lookup"><span data-stu-id="28867-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="28867-227">Este componente puede registrar una condición de error cuando el valor de la variable DataReady es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="28867-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="28867-228">Este valor indica que no hay datos modificados disponibles antes del inicio del intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="28867-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="28867-229">Este componente también puede registrar un error de tiempo de espera cuando se alcanza el valor de la variable TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="28867-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="28867-230">Este valor indica que el bucle ha comprobado la existencia de datos el número de veces especificado pero los datos aún no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="28867-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="28867-231">Sin esta prueba u otra similar, el paquete podría ejecutarse indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="28867-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="28867-232">Para configurar una tarea Script opcional de forma que registre una condición de error</span><span class="sxs-lookup"><span data-stu-id="28867-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="28867-233">Si desea informar del error o de que se ha superado el tiempo de espera escribiendo un mensaje en el registro, configure el registro para el paquete.</span><span class="sxs-lookup"><span data-stu-id="28867-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="28867-234">Para más información, vea [Habilitar el registro de paquetes en SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28867-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="28867-235">Dentro del contenedor de bucles For, agregue una tarea Script.</span><span class="sxs-lookup"><span data-stu-id="28867-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="28867-236">Conecte a la nueva tarea Script la tarea Ejecutar SQL que hace la consulta para determinar si los datos modificados están preparados.</span><span class="sxs-lookup"><span data-stu-id="28867-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="28867-237">Para obtener la restricción de precedencia que conecta la tarea Ejecutar SQL a la tarea Script, abra el **Editor de restricciones de precedencia** y seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28867-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="28867-238">En **Operación de evaluación**, seleccione **Expresión y restricción**.</span><span class="sxs-lookup"><span data-stu-id="28867-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="28867-239">En **Valor**, seleccione **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="28867-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="28867-240">El valor de restricción **Correcto** se refiere a la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="28867-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="28867-241">En este caso, la tarea Ejecutar SQL debe haberse realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="28867-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="28867-242">Para **Expresión**, escriba `@DataReady == 1 || @DataReady == 5`.</span><span class="sxs-lookup"><span data-stu-id="28867-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="28867-243">Seleccione **AND lógico. Todas las restricciones deben evaluarse como True**, si no está ya seleccionada.</span><span class="sxs-lookup"><span data-stu-id="28867-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="28867-244">Esta selección requiere que ambas condiciones, la restricción y la expresión, sean true.</span><span class="sxs-lookup"><span data-stu-id="28867-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="28867-245">En el **Editor de la tarea Script**, en la página **Script** del editor, para **ReadOnlyVariables**, seleccione **User::DataReady** y **User::ExtractStartTime** en la lista para que sus valores estén disponibles para el script.</span><span class="sxs-lookup"><span data-stu-id="28867-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="28867-246">Si desea incluir datos de ciertas variables del sistema (por ejemplo, System::PackageName) en la información que escribe en el registro, seleccione también dichas variables.</span><span class="sxs-lookup"><span data-stu-id="28867-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="28867-247">En el **Editor de la tarea Script**, en la página **Script** , haga clic en **Modificar script** para abrir el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="28867-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="28867-248">En el procedimiento Main, escriba el código para registrar un error llamando al método `Dts.Log` o el código para provocar un evento llamando a uno de los métodos de la interfaz `Dts.Events`.</span><span class="sxs-lookup"><span data-stu-id="28867-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="28867-249">Para informar del error al paquete, devuelva `Dts.TaskResult = Dts.Results.Failure`.</span><span class="sxs-lookup"><span data-stu-id="28867-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="28867-250">El ejemplo siguiente muestra cómo escribir un mensaje en el registro.</span><span class="sxs-lookup"><span data-stu-id="28867-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="28867-251">Para obtener más información, consulte [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md)y [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="28867-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="28867-252">Cierre el entorno de desarrollo de script y el **Editor de la tarea Script**.</span><span class="sxs-lookup"><span data-stu-id="28867-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="28867-253">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="28867-253">Next Step</span></span>  
 <span data-ttu-id="28867-254">Después de determinar que los datos modificados están listos, el paso siguiente consiste en preparar la consulta de los mismos.</span><span class="sxs-lookup"><span data-stu-id="28867-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="28867-255">**Tema siguiente:** [Preparar para consultar datos modificados](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="28867-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
