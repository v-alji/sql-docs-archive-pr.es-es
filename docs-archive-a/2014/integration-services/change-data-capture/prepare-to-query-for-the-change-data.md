---
title: Preparar para consultar datos modificados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663051"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="9ca74-102">Preparar para consultar datos modificados</span><span class="sxs-lookup"><span data-stu-id="9ca74-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="9ca74-103">En el flujo de control de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de datos modificados, la tercera y última tarea consiste en preparar la consulta de los datos modificados y agregar una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca74-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ca74-104">La segunda tarea para el flujo de control consiste en asegurarse de que están listos los datos modificados para el intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9ca74-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="9ca74-105">Para obtener más información sobre esta tarea, vea [Determinar si los datos modificados están preparados](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="9ca74-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="9ca74-106">Para obtener una descripción del proceso general de diseño del flujo de control, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="9ca74-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="9ca74-107">Consideraciones de diseño</span><span class="sxs-lookup"><span data-stu-id="9ca74-107">Design Considerations</span></span>  
 <span data-ttu-id="9ca74-108">Para recuperar los datos modificados, se llama a una función con valores de tabla de Transact-SQL que acepta los extremos del intervalo como parámetros de entrada y devuelve los datos modificados para el intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="9ca74-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="9ca74-109">Un componente de origen del flujo de datos llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="9ca74-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="9ca74-110">Para obtener información sobre este componente de origen, vea [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="9ca74-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="9ca74-111">Los componentes de origen de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que se han usado con más frecuencia, como son el origen de OLE DB, el origen de ADO y el origen de ADO NET, no pueden derivar información de parámetros para una función con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="9ca74-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="9ca74-112">Por consiguiente, la mayoría de los orígenes no pueden llamar directamente a una función con parámetros.</span><span class="sxs-lookup"><span data-stu-id="9ca74-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="9ca74-113">Dispone de dos opciones de diseño para pasar los parámetros de entrada a la función:</span><span class="sxs-lookup"><span data-stu-id="9ca74-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="9ca74-114">**Ensamblar la consulta con parámetros como una cadena**.</span><span class="sxs-lookup"><span data-stu-id="9ca74-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="9ca74-115">Puede utilizar una tarea Script o una tarea Ejecutar SQL para ensamblar una cadena SQL dinámica cuyos valores de parámetros estén codificados de forma rígida en la cadena.</span><span class="sxs-lookup"><span data-stu-id="9ca74-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="9ca74-116">A continuación, puede almacenar esta cadena en una variable de paquete y utilizarla para establecer la propiedad SqlCommand de un componente de origen.</span><span class="sxs-lookup"><span data-stu-id="9ca74-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="9ca74-117">Este enfoque tiene éxito porque el componente de origen ya no requiere la información de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="9ca74-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ca74-118">Un script precompilado produce menos sobrecarga que una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="9ca74-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="9ca74-119">**Utilizar un contenedor con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="9ca74-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="9ca74-120">También puede crear un procedimiento almacenado con parámetros como un contenedor que llama a la función con valores de tabla con parámetros.</span><span class="sxs-lookup"><span data-stu-id="9ca74-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="9ca74-121">Este enfoque tiene éxito porque un componente de origen puede derivar correctamente la información de parámetros para un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="9ca74-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="9ca74-122">En este tema se utiliza la primera opción de diseño y se ensambla una consulta con parámetros como una cadena.</span><span class="sxs-lookup"><span data-stu-id="9ca74-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="9ca74-123">Preparar la consulta</span><span class="sxs-lookup"><span data-stu-id="9ca74-123">Preparing the Query</span></span>  
 <span data-ttu-id="9ca74-124">Antes de poder concatenar los valores de los parámetros de entrada en una sola cadena de consulta, se deben establecer las variables de paquete necesarias para la consulta.</span><span class="sxs-lookup"><span data-stu-id="9ca74-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="9ca74-125">Para establecer las variables de paquetes</span><span class="sxs-lookup"><span data-stu-id="9ca74-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="9ca74-126">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la ventana **Variables** , cree una variable con un tipo de datos de cadena para guardar la cadena de consulta devuelta por la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="9ca74-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="9ca74-127">En este ejemplo se utiliza el nombre de variable SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="9ca74-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="9ca74-128">Una vez creada la variable de paquete, puede utilizar una tarea Script o una tarea Ejecutar SQL para concatenar los valores de los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="9ca74-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="9ca74-129">En los dos procedimientos siguientes se describe cómo configurar estos componentes.</span><span class="sxs-lookup"><span data-stu-id="9ca74-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="9ca74-130">Para utilizar una tarea Script para concatenar la cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="9ca74-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="9ca74-131">En la pestaña **Flujo de control** , agregue una tarea Script al paquete después del contenedor de bucles For y conecte dicho contenedor a la tarea.</span><span class="sxs-lookup"><span data-stu-id="9ca74-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ca74-132">En este procedimiento se supone que el paquete realiza una carga incremental desde una única tabla.</span><span class="sxs-lookup"><span data-stu-id="9ca74-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="9ca74-133">Si el paquete carga de varias tablas y tiene un paquete primario con varios paquetes secundarios, esta tarea se agregaría como primer componente a cada paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="9ca74-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="9ca74-134">Para obtener más información, vea [Realizar una carga incremental de varias tablas](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9ca74-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="9ca74-135">En el **Editor de la tarea Script**, en la página **Script** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ca74-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="9ca74-136">Para **ReadOnlyVariables**, seleccione **User::DataReady**, **User::ExtractStartTime**y **User::ExtractEndTime** en la lista.</span><span class="sxs-lookup"><span data-stu-id="9ca74-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="9ca74-137">Para **ReadWriteVariables**, seleccione User::SqlDataQuery en la lista.</span><span class="sxs-lookup"><span data-stu-id="9ca74-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="9ca74-138">En el **Editor de la tarea Script**, en la página **Script** , haga clic en **Modificar script** para abrir el entorno de desarrollo de script.</span><span class="sxs-lookup"><span data-stu-id="9ca74-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="9ca74-139">En el procedimiento Main, escriba uno de los segmentos de código siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ca74-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="9ca74-140">Si está programando en C#, escriba las líneas de código siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ca74-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="9ca74-141">\- O bien</span><span class="sxs-lookup"><span data-stu-id="9ca74-141">\- or -</span></span>  
  
    -   <span data-ttu-id="9ca74-142">Si está programando en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], escriba las líneas de código siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ca74-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="9ca74-143">Deje la línea de código predeterminada que devuelve `DtsExecResult.Success` de la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="9ca74-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="9ca74-144">Cierre el entorno de desarrollo de script y el **Editor de la tarea Script**.</span><span class="sxs-lookup"><span data-stu-id="9ca74-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="9ca74-145">Para utilizar una tarea Ejecutar SQL para concatenar la cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="9ca74-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="9ca74-146">En la pestaña **Flujo de control** , agregue una tarea Ejecutar SQL al paquete después del contenedor de bucles For y conecte dicho contenedor a esta tarea.</span><span class="sxs-lookup"><span data-stu-id="9ca74-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ca74-147">En este procedimiento se supone que el paquete realiza una carga incremental desde una única tabla.</span><span class="sxs-lookup"><span data-stu-id="9ca74-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="9ca74-148">Si el paquete carga de varias tablas y tiene un paquete primario con varios paquetes secundarios, esta tarea se agregaría como primer componente a cada paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="9ca74-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="9ca74-149">Para obtener más información, vea [Realizar una carga incremental de varias tablas](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9ca74-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="9ca74-150">En el **Editor de la tarea Ejecutar SQL**, en la página **General** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ca74-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="9ca74-151">En **Conjunto de resultados**, seleccione **Fila única**.</span><span class="sxs-lookup"><span data-stu-id="9ca74-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="9ca74-152">Configure una conexión válida con una base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9ca74-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="9ca74-153">En **SQLSourceType**, seleccione **Entrada directa**.</span><span class="sxs-lookup"><span data-stu-id="9ca74-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="9ca74-154">En **SQLStatement**, escriba la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="9ca74-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="9ca74-155">La cláusula `else` de este ejemplo genera una consulta para la carga inicial de los datos modificados pasando un valor NULL para la fecha y hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="9ca74-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="9ca74-156">En este ejemplo no se contempla el escenario en el que los cambios que se realizaron antes de habilitar la captura de datos modificados también deben cargarse en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca74-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="9ca74-157">En la página **Asignación de parámetros** del **Editor de la tarea Ejecutar SQL**, haga la asignación siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ca74-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="9ca74-158">Asigne la variable DataReady al parámetro 0.</span><span class="sxs-lookup"><span data-stu-id="9ca74-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="9ca74-159">Asigne la variable ExtractStartTime al parámetro 1.</span><span class="sxs-lookup"><span data-stu-id="9ca74-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="9ca74-160">Asigne la variable ExtractEndTime al parámetro 2.</span><span class="sxs-lookup"><span data-stu-id="9ca74-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="9ca74-161">En la página **Conjunto de resultados** del **Editor de la tarea Ejecutar SQL**, asigne el nombre del resultado a la variable SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="9ca74-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="9ca74-162">El nombre del resultado es el nombre de la única columna que se devuelve, SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="9ca74-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="9ca74-163">Los procedimientos anteriores configuran una tarea que prepara una cadena de consulta con valores de cadena codificados de forma rígida para los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="9ca74-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="9ca74-164">El código siguiente es un ejemplo de este tipo de cadena de consulta:</span><span class="sxs-lookup"><span data-stu-id="9ca74-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="9ca74-165">Agregar una tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca74-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="9ca74-166">El último paso para diseñar el flujo de control para el paquete consiste en agregar una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca74-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="9ca74-167">Para agregar una tarea Flujo de datos y completar el flujo de control</span><span class="sxs-lookup"><span data-stu-id="9ca74-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="9ca74-168">En la pestaña **Flujo de control** , agregue una tarea Flujo de Datos y conecte la tarea que concatenó la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="9ca74-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="9ca74-169">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="9ca74-169">Next Step</span></span>  
 <span data-ttu-id="9ca74-170">Después de preparar la cadena de consulta y configurar la tarea Flujo de Datos, el paso siguiente consiste en crear la función con valores de tabla que recuperará los datos modificados de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca74-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="9ca74-171">**Tema siguiente:** [Crear la función para recuperar los datos modificados](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="9ca74-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
