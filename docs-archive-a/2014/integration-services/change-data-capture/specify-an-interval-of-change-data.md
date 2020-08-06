---
title: Especificar un intervalo de datos modificados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671121"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="e6247-102">Especificar un intervalo de datos modificados</span><span class="sxs-lookup"><span data-stu-id="e6247-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="e6247-103">En el flujo de control de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de datos modificados, la primera tarea consiste en calcular los extremos del intervalo de cambios.</span><span class="sxs-lookup"><span data-stu-id="e6247-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="e6247-104">Estos extremos son valores `datetime` y se almacenarán en variables de paquete para su uso posterior en el paquete.</span><span class="sxs-lookup"><span data-stu-id="e6247-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6247-105">Para obtener una descripción del proceso general de diseño del flujo de control, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="e6247-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="e6247-106">Configurar variables de paquete para los extremos</span><span class="sxs-lookup"><span data-stu-id="e6247-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="e6247-107">Antes de configurar la tarea Ejecutar SQL para calcular los extremos, será necesario definir las variables de paquete que almacenarán dichos extremos.</span><span class="sxs-lookup"><span data-stu-id="e6247-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="e6247-108">Para establecer las variables de paquetes</span><span class="sxs-lookup"><span data-stu-id="e6247-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="e6247-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra un nuevo proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6247-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="e6247-110">En la ventana **Variables** , cree las variables siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6247-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="e6247-111">Cree una variable con el tipo de datos `datetime` para almacenar el punto inicial del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e6247-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="e6247-112">En este ejemplo se utiliza el nombre de variable ExtractStartTime.</span><span class="sxs-lookup"><span data-stu-id="e6247-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="e6247-113">Cree otra variable con el tipo de datos `datetime` para almacenar el punto final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e6247-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="e6247-114">En este ejemplo se utiliza el nombre de variable ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="e6247-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="e6247-115">Si calcula los extremos en un paquete primario que ejecuta varios paquetes secundarios, puede utilizar las configuraciones de variables de paquete primario para pasar los valores de estas variables a cada paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="e6247-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="e6247-116">Para más información, vea [Tarea Ejecutar paquete](../control-flow/execute-package-task.md) y [Usar los valores de variables y parámetros en un paquete secundario](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="e6247-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="e6247-117">Calcular un punto inicial y un punto final para los datos modificados</span><span class="sxs-lookup"><span data-stu-id="e6247-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="e6247-118">Después de establecer las variables de paquete para los extremos del intervalo, puede calcular los valores reales para dichos extremos y asignarlos a las variables de paquete correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e6247-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="e6247-119">Dado que esos extremos son valores `datetime`, deberá usar funciones que puedan calcular o utilizar valores `datetime`.</span><span class="sxs-lookup"><span data-stu-id="e6247-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="e6247-120">Tanto el lenguaje de expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] como Transact-SQL tienen funciones que operan con valores `datetime`:</span><span class="sxs-lookup"><span data-stu-id="e6247-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="e6247-121">Funciones del lenguaje de expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que operan con valores `datetime`</span><span class="sxs-lookup"><span data-stu-id="e6247-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="e6247-122">DATEADD &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-123">DATEDIFF &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-124">DATEPART &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-125">DAY &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-126">GETDATE &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-127">GETUTCDATE &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-128">MONTH &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="e6247-129">YEAR &#40;expresión de SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6247-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="e6247-130">Funciones de Transact-SQL que operan con valores `datetime`</span><span class="sxs-lookup"><span data-stu-id="e6247-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="e6247-131">[Tipos de datos y funciones de fecha y hora &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6247-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="e6247-132">Antes de utilizar cualquiera de estas funciones de `datetime` para calcular los extremos, deberá determinar si el intervalo es fijo y se produce con regularidad.</span><span class="sxs-lookup"><span data-stu-id="e6247-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="e6247-133">Por lo general, se prefiere aplicar regularmente en las tablas de destino los cambios que se han producido en las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="e6247-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="e6247-134">Por ejemplo, puede aplicar esos cambios cada hora, diariamente o incluso semanalmente.</span><span class="sxs-lookup"><span data-stu-id="e6247-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="e6247-135">Una vez que decida si su intervalo de cambios es fijo o aleatorio, podrá calcular los extremos:</span><span class="sxs-lookup"><span data-stu-id="e6247-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="e6247-136">**Calcular la fecha y hora de inicio**.</span><span class="sxs-lookup"><span data-stu-id="e6247-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="e6247-137">Utilice la fecha y hora de finalización de la carga anterior como los valores actuales.</span><span class="sxs-lookup"><span data-stu-id="e6247-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="e6247-138">Si utiliza un intervalo fijo para las cargas incrementales, puede calcular este valor mediante las funciones de `datetime` de Transact-SQL o del lenguaje de expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6247-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="e6247-139">De lo contrario, es posible que tenga que conservar los extremos entre las ejecuciones y utilizar una tarea Ejecutar SQL o una tarea Script para cargar el extremo anterior.</span><span class="sxs-lookup"><span data-stu-id="e6247-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="e6247-140">**Calcular la fecha y hora de finalización**.</span><span class="sxs-lookup"><span data-stu-id="e6247-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="e6247-141">Si utiliza un intervalo fijo para las cargas incrementales, calcule la fecha y hora de finalización actuales como un desplazamiento de la fecha y hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="e6247-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="e6247-142">De nuevo, puede calcular este valor mediante las `datetime` funciones de Transact-SQL o del lenguaje de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expresiones.</span><span class="sxs-lookup"><span data-stu-id="e6247-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="e6247-143">En el procedimiento siguiente, el intervalo de cambios utiliza un intervalo fijo y da por supuesto que el paquete de la carga incremental se ejecuta diariamente sin excepciones.</span><span class="sxs-lookup"><span data-stu-id="e6247-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="e6247-144">De lo contrario, se perderían los datos modificados para los intervalos que faltan.</span><span class="sxs-lookup"><span data-stu-id="e6247-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="e6247-145">El punto inicial del intervalo es la medianoche de anteayer, es decir, hace unas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="e6247-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="e6247-146">El punto final del intervalo es la medianoche de ayer, es decir, la noche anterior, hace unas 0 a 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e6247-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="e6247-147">Para calcular el punto inicial y el punto final del intervalo de captura</span><span class="sxs-lookup"><span data-stu-id="e6247-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="e6247-148">En la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue una tarea Ejecutar SQL al paquete.</span><span class="sxs-lookup"><span data-stu-id="e6247-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="e6247-149">Abra el **Editor de la tarea Ejecutar SQL**y en la página **General** del editor, seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6247-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="e6247-150">En **Conjunto de resultados**, seleccione **Fila única**.</span><span class="sxs-lookup"><span data-stu-id="e6247-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="e6247-151">Configure una conexión válida con una base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="e6247-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="e6247-152">En **SQLSourceType**, seleccione **Entrada directa**.</span><span class="sxs-lookup"><span data-stu-id="e6247-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="e6247-153">En **SQLStatement**, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="e6247-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="e6247-154">En la página **Conjunto de resultados** del **Editor de la tarea Ejecutar SQL**, asigne el resultado de ExtractStartTime a la variable de paquete ExtractStartTime y el resultado de ExtractEndTime a la variable de paquete ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="e6247-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6247-155">Al usar una expresión para establecer el valor de una variable de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], dicha expresión se evalúa cada vez que se accede al valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="e6247-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e6247-156">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="e6247-156">Next Step</span></span>  
 <span data-ttu-id="e6247-157">Una vez calculados los puntos inicial y final de un intervalo de cambios, el paso siguiente consiste en determinar si están listos los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="e6247-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="e6247-158">**Tema siguiente:** [Determinar si los datos modificados están preparados](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="e6247-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6247-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6247-159">See Also</span></span>  
 <span data-ttu-id="e6247-160">[Usar variables en paquetes](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="e6247-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="e6247-161">[Expresiones de Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="e6247-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="e6247-162">[Tarea Ejecutar SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="e6247-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="e6247-163">Tarea Script</span><span class="sxs-lookup"><span data-stu-id="e6247-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
