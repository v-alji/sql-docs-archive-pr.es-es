---
title: Aplicar los cambios al destino | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677790"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="50de0-102">Aplicar los cambios al destino</span><span class="sxs-lookup"><span data-stu-id="50de0-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="50de0-103">En el flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de datos modificados, la tercera y última tarea consiste en aplicar los cambios al destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="50de0-104">Necesitará un componente para aplicar las inserciones, otro para aplicar las actualizaciones y otro más para aplicar las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50de0-105">La segunda tarea para diseñar el flujo de datos de un paquete que realiza una carga incremental de datos modificados consiste en separar las inserciones, las actualizaciones y las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="50de0-106">Para obtener más información sobre este componente, vea [Procesar inserciones, actualizaciones y eliminaciones](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="50de0-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="50de0-107">Para obtener una descripción del proceso general de creación de un paquete que realiza una carga incremental de los datos modificados, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="50de0-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="50de0-108">Aplicar las inserciones</span><span class="sxs-lookup"><span data-stu-id="50de0-108">Applying Inserts</span></span>  
 <span data-ttu-id="50de0-109">Para aplicar las inserciones, utilice un destino de OLE DB, ya que las nuevas filas no requieren ningún tratamiento especial.</span><span class="sxs-lookup"><span data-stu-id="50de0-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="50de0-110">Para procesar las inserciones mediante un destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="50de0-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="50de0-111">En la pestaña **Flujo de datos** , agregue un destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="50de0-112">Conecte la salida que contiene las inserciones de la transformación División condicional al destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="50de0-113">En el **Editor de destino de OLE DB**, en la página **Administrador de conexiones** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="50de0-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="50de0-114">Seleccione o cree un administrador de conexiones OLE DB para la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="50de0-115">Seleccione una opción de **Modo de acceso a datos** y, a continuación, seleccione la tabla de destino o escriba una instrucción SQL que contenga las columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="50de0-116">En la página **Asignaciones** del editor, asigne las columnas apropiadas de los datos modificados a la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="50de0-117">Aplicar las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="50de0-117">Applying Updates</span></span>  
 <span data-ttu-id="50de0-118">Para aplicar las actualizaciones, utilice una transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="50de0-119">La razón para usar esta transformación es que hay que utilizar una instrucción UPDATE con parámetros para actualizar las filas de una en una con los nuevos valores de las columnas.</span><span class="sxs-lookup"><span data-stu-id="50de0-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50de0-120">También puede utilizar los componentes de destino para aplicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="50de0-121">Al emplear este método, se usan los componentes de destino para guardar las filas en tablas temporales que se crean para este propósito.</span><span class="sxs-lookup"><span data-stu-id="50de0-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="50de0-122">Después, se usan las tareas Ejecutar SQL para realizar operaciones de actualización y eliminación masivas con el destino a partir de las tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="50de0-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="50de0-123">Para procesar las actualizaciones mediante una transformación Comando de OLE DB</span><span class="sxs-lookup"><span data-stu-id="50de0-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="50de0-124">En la pestaña **Flujo de datos** , agregue una transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="50de0-125">Conecte la salida que contiene las actualizaciones de la transformación División condicional a la transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="50de0-126">En la pestaña **Editor avanzado para Comando de OLE DB**, en la pestaña **Administrador de conexiones** , seleccione o cree un administrador de conexiones de OLE DB para la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="50de0-127">En el **Editor avanzado para Comando de OLE DB**, en la pestaña **Propiedades de componente** , escriba una instrucción UPDATE con parámetros para **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="50de0-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="50de0-128">Por ejemplo, una instrucción UPDATE para una tabla de clientes podría tener la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="50de0-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="50de0-129">En la pestaña **Asignaciones de columnas** del editor, asigne las columnas apropiadas de los datos modificados a los parámetros de la instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="50de0-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="50de0-130">Aplicar las eliminaciones</span><span class="sxs-lookup"><span data-stu-id="50de0-130">Applying Deletes</span></span>  
 <span data-ttu-id="50de0-131">Para aplicar las eliminaciones, utilice una transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="50de0-132">La razón para usar esta transformación es que hay que utilizar una instrucción DELETE con parámetros que elimina las filas de una en una basándose en el valor de columna que identifica la fila de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="50de0-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50de0-133">También puede utilizar los componentes de destino para aplicar las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="50de0-134">Al emplear este método, se usan los componentes de destino para guardar las filas en tablas temporales que se crean para este propósito.</span><span class="sxs-lookup"><span data-stu-id="50de0-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="50de0-135">Después, se usan las tareas Ejecutar SQL para realizar operaciones de actualización y eliminación masivas con el destino a partir de las tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="50de0-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="50de0-136">Para procesar las eliminaciones mediante una transformación Comando de OLE DB</span><span class="sxs-lookup"><span data-stu-id="50de0-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="50de0-137">En la pestaña **Flujo de datos** , agregue una transformación Comando de OLE DB al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="50de0-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="50de0-138">Conecte la salida que contiene las eliminaciones de la transformación División condicional a la transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="50de0-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="50de0-139">Abra el Editor avanzado para configurar la transformación.</span><span class="sxs-lookup"><span data-stu-id="50de0-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="50de0-140">En la pestaña **Editor avanzado para Comando de OLE DB**, en la pestaña **Administrador de conexiones** , seleccione o cree un administrador de conexiones de OLE DB para la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="50de0-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="50de0-141">En el **Editor avanzado para Comando de OLE DB**, en la pestaña **Propiedades de componente** , escriba una instrucción DELETE con parámetros para **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="50de0-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="50de0-142">Por ejemplo, una instrucción DELETE para una tabla de clientes podría tener la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="50de0-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="50de0-143">En la pestaña **Asignaciones de columnas** del editor, asigne la columna apropiada de los datos modificados al parámetro de la instrucción DELETE.</span><span class="sxs-lookup"><span data-stu-id="50de0-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="50de0-144">Optimizar inserciones y actualizaciones mediante la funcionalidad MERGE</span><span class="sxs-lookup"><span data-stu-id="50de0-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="50de0-145">Puede optimizar el procesamiento de inserciones y actualizaciones si combina ciertas opciones de captura de datos modificados con el uso de la palabra clave MERGE de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="50de0-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="50de0-146">Para obtener más información sobre la palabra clave MERGE, vea [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50de0-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="50de0-147">En la instrucción Transact-SQL que recupera los datos modificados, puede especificar *all with merge* como el valor del parámetro *row_filter_option* al llamar a la función **cdc.fn_cdc_get_net_changes_<capture_instance>** .</span><span class="sxs-lookup"><span data-stu-id="50de0-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="50de0-148">Esta función de captura de datos modificados funciona con más eficacia cuando no tiene que realizar el procesamiento adicional necesario para distinguir las inserciones de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="50de0-149">Al especificar el valor del parámetro *all with merge* , el valor **__$operation** de los datos modificados es 1 para las eliminaciones o 5 para los cambios producidos por las inserciones o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="50de0-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="50de0-150">Para obtener más información sobre la función de Transact-SQL que se ha usado para recuperar los datos modificados, vea [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md). Una vez recuperados los cambios con el valor del parámetro *all with merge* , podrá aplicar las eliminaciones y almacenar las filas restantes en una tabla temporal o de ensayo.</span><span class="sxs-lookup"><span data-stu-id="50de0-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="50de0-151">A continuación, en una tarea Ejecutar SQL de nivel inferior, puede utilizar una única instrucción MERGE para aplicar al destino todas las inserciones o actualizaciones de la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="50de0-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
