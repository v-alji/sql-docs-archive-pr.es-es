---
title: Asignar parámetros de consulta a variables en una tarea ejecutar SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672159"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="9c819-102">asignar parámetros de consulta a variables en una tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="9c819-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="9c819-103">En este tema se describe cómo utilizar una instrucción SQL con parámetros en la tarea Ejecutar SQL, y crear asignaciones entre las variables y los parámetros de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="9c819-104">Para más información sobre la tarea Ejecutar SQL, los marcadores de parámetros y los nombres de parámetros que se usan con diferentes tipos de conexión, vea [Tarea Ejecutar SQL](control-flow/execute-sql-task.md) y [Parámetros y códigos de retorno en la tarea Ejecutar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="9c819-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="9c819-105">Para asignar un parámetro de consulta a una variable</span><span class="sxs-lookup"><span data-stu-id="9c819-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="9c819-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="9c819-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="9c819-107">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="9c819-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9c819-108">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="9c819-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="9c819-109">Si el paquete no incluye en ese momento una tarea Ejecutar SQL, agregue una al flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="9c819-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="9c819-110">Para obtener más información, vea [Agregar o eliminar una tarea o un contenedor en un flujo de control](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="9c819-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="9c819-111">.</span><span class="sxs-lookup"><span data-stu-id="9c819-111">.</span></span>  
  
5.  <span data-ttu-id="9c819-112">Haga doble clic en la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="9c819-113">Proporcione un comando SQL con parámetros en una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="9c819-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="9c819-114">Use entrada directa y escriba el comando SQL en la propiedad SQLStatement.</span><span class="sxs-lookup"><span data-stu-id="9c819-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="9c819-115">Use entrada directa, haga clic en **Generar consulta**y luego cree un comando SQL mediante las herramientas gráficas proporcionadas por el Generador de consultas.</span><span class="sxs-lookup"><span data-stu-id="9c819-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="9c819-116">Use una conexión de archivo y luego haga referencia al archivo que contiene el comando SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="9c819-117">Use una variable y luego haga referencia a la variable que contiene el comando SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="9c819-118">Los marcadores de parámetros que utiliza en las instrucciones SQL con parámetros dependen del tipo de conexión que utiliza la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="9c819-119">Tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="9c819-119">Connection type</span></span>|<span data-ttu-id="9c819-120">Marcador de parámetro</span><span class="sxs-lookup"><span data-stu-id="9c819-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="9c819-121">ADO</span><span class="sxs-lookup"><span data-stu-id="9c819-121">ADO</span></span>|<span data-ttu-id="9c819-122">?</span><span class="sxs-lookup"><span data-stu-id="9c819-122">?</span></span>|  
    |<span data-ttu-id="9c819-123">ADO.NET y SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="9c819-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="9c819-124">ODBC</span><span class="sxs-lookup"><span data-stu-id="9c819-124">ODBC</span></span>|<span data-ttu-id="9c819-125">?</span><span class="sxs-lookup"><span data-stu-id="9c819-125">?</span></span>|  
    |<span data-ttu-id="9c819-126">EXCEL y OLE DB</span><span class="sxs-lookup"><span data-stu-id="9c819-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="9c819-127">?</span><span class="sxs-lookup"><span data-stu-id="9c819-127">?</span></span>|  
  
     <span data-ttu-id="9c819-128">La tabla siguiente enumera ejemplos del comando SELECT por tipo de Administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9c819-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="9c819-129">Los parámetros proporcionan los valores de filtro en las cláusulas WHERE.</span><span class="sxs-lookup"><span data-stu-id="9c819-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="9c819-130">Los ejemplos utilizan el comando SELECT para devolver los productos de la tabla **Product** de [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] que tienen un valor de **ProductID** mayor y menor que los valores especificados por dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c819-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="9c819-131">Tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="9c819-131">Connection type</span></span>|<span data-ttu-id="9c819-132">Sintaxis de SELECT</span><span class="sxs-lookup"><span data-stu-id="9c819-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="9c819-133">EXCEL, ODBC y OLE DB</span><span class="sxs-lookup"><span data-stu-id="9c819-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="9c819-134">ADO</span><span class="sxs-lookup"><span data-stu-id="9c819-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="9c819-135">Para obtener ejemplos de cómo usar parámetros con procedimientos almacenados, vea [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="9c819-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="9c819-136">Haga clic en **Asignación de parámetros**.</span><span class="sxs-lookup"><span data-stu-id="9c819-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="9c819-137">Para agregar una asignación de parámetros, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c819-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="9c819-138">Escriba un nombre en el cuadro **Nombre de parámetro** .</span><span class="sxs-lookup"><span data-stu-id="9c819-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="9c819-139">Los nombres de parámetros que utiliza dependen del tipo de conexión que utiliza la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="9c819-140">Tipo de conexión</span><span class="sxs-lookup"><span data-stu-id="9c819-140">Connection type</span></span>|<span data-ttu-id="9c819-141">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="9c819-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="9c819-142">ADO</span><span class="sxs-lookup"><span data-stu-id="9c819-142">ADO</span></span>|<span data-ttu-id="9c819-143">Param1, Param2…</span><span class="sxs-lookup"><span data-stu-id="9c819-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="9c819-144">ADO.NET y SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="9c819-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="9c819-145">ODBC</span><span class="sxs-lookup"><span data-stu-id="9c819-145">ODBC</span></span>|<span data-ttu-id="9c819-146">1, 2, 3…</span><span class="sxs-lookup"><span data-stu-id="9c819-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="9c819-147">EXCEL y OLE DB</span><span class="sxs-lookup"><span data-stu-id="9c819-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="9c819-148">0, 1, 2, 3…</span><span class="sxs-lookup"><span data-stu-id="9c819-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="9c819-149">En la lista **Nombre de variable** , seleccione una variable.</span><span class="sxs-lookup"><span data-stu-id="9c819-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="9c819-150">Para más información, vea [Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="9c819-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="9c819-151">En la lista **Dirección** , especifique si el parámetro es una entrada, una salida o un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="9c819-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="9c819-152">En la lista **Tipo de datos** , seleccione el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="9c819-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9c819-153">El tipo de datos del parámetro debe ser compatible con el tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="9c819-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="9c819-154">Repita los pasos del 8 al 11 para cada parámetro en la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9c819-155">El orden de las asignaciones de parámetros debe ser el mismo que el orden en que aparecen los parámetros en la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9c819-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="9c819-156">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c819-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c819-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c819-157">See Also</span></span>  
 <span data-ttu-id="9c819-158">[Tarea ejecutar SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="9c819-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="9c819-159">[Parámetros y códigos de retorno en la tarea ejecutar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="9c819-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="9c819-160">Variables de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9c819-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
