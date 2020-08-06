---
title: Realizar una carga incremental de varias tablas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669810"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="6e3d8-102">Realizar una carga incremental de varias tablas</span><span class="sxs-lookup"><span data-stu-id="6e3d8-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="6e3d8-103">En el tema [Mejorar las cargas incrementales con la captura de datos modificados](change-data-capture-ssis.md), el diagrama muestra un paquete básico que realiza una carga incremental en una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="6e3d8-104">Sin embargo, cargar una tabla no es una acción tan común como realizar una carga incremental de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="6e3d8-105">Cuando se realiza una carga incremental de varias tablas, algunos pasos se tienen que realizar una vez para todas las tablas y otros se tienen que repetir para cada tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="6e3d8-106">Tiene varias opciones para implementar estos pasos en [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6e3d8-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="6e3d8-107">Utilizar un paquete primario y varios paquetes secundarios.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="6e3d8-108">Utilizar varias tareas Flujo de datos en un único paquete.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="6e3d8-109">Cargar varias tablas mediante un paquete primario y varios paquetes secundarios</span><span class="sxs-lookup"><span data-stu-id="6e3d8-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="6e3d8-110">Puede usar un paquete primario para realizar aquellos pasos que solo deben seguirse una vez.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="6e3d8-111">Los paquetes secundarios realizarán los pasos que se deben efectuar para cada tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="6e3d8-112">Para crear un paquete primario que realice los pasos que solo se deben efectuar una vez</span><span class="sxs-lookup"><span data-stu-id="6e3d8-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="6e3d8-113">Cree un paquete primario.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="6e3d8-114">En el flujo de control, utilice una tarea Ejecutar SQL o expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para calcular los extremos.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="6e3d8-115">Para obtener un ejemplo de cómo calcular los puntos de conexión, vea [Especificar un intervalo de datos modificados](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="6e3d8-116">Si es necesario, utilice un contenedor de bucles For para retrasar la ejecución hasta que los datos modificados para el período seleccionado estén listos.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="6e3d8-117">Para obtener un ejemplo de un contenedor de bucles For, vea [Determinar si los datos modificados están preparados](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="6e3d8-118">Utilice varias tareas Ejecutar paquete para ejecutar los paquetes secundarios para cada tabla que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="6e3d8-119">Pase los extremos calculados en el paquete primario a cada paquete secundario mediante configuraciones de variable de paquete primario.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="6e3d8-120">Para más información, vea [Tarea Ejecutar paquete](../control-flow/execute-package-task.md) y [Usar los valores de variables y parámetros en un paquete secundario](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="6e3d8-121">Para crear paquetes secundarios que realicen los pasos que se deben efectuar para cada tabla de origen</span><span class="sxs-lookup"><span data-stu-id="6e3d8-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="6e3d8-122">Cree un paquete secundario para cada tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="6e3d8-123">En el flujo de control, utilice una tarea Script o una tarea Ejecutar SQL para ensamblar la instrucción SQL que se usará para consultar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="6e3d8-124">Para obtener un ejemplo de cómo ensamblar la consulta, vea [Preparar para consultar datos modificados](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="6e3d8-125">Utilice una única tarea Flujo de datos en cada paquete secundario para cargar los datos modificados y aplicarlos al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="6e3d8-126">Configure el flujo de datos como se describe en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e3d8-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="6e3d8-127">En el flujo de datos, utilice un componente de origen para consultar en las tablas de cambios los cambios comprendidos entre los extremos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="6e3d8-128">Para obtener un ejemplo de cómo consultar las tablas de cambios, vea [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="6e3d8-129">Use la transformación División condicional para dirigir las inserciones, las actualizaciones y las eliminaciones a salidas diferentes para procesarlas apropiadamente.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="6e3d8-130">Para obtener un ejemplo de cómo configurar esta transformación para dirigir la salida, vea [Procesar inserciones, actualizaciones y eliminaciones](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="6e3d8-131">Use un componente de destino para aplicar las inserciones al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="6e3d8-132">Use transformaciones Comando de OLE DB con instrucciones UPDATE y DELETE con parámetros para aplicar las actualizaciones y las eliminaciones al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="6e3d8-133">Para obtener un ejemplo de cómo usar esta transformación para aplicar las actualizaciones y eliminaciones, vea [Aplicar los cambios al destino](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="6e3d8-134">Cargar varias tablas mediante varias tareas Flujo de datos en un único paquete</span><span class="sxs-lookup"><span data-stu-id="6e3d8-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="6e3d8-135">También puede utilizar un único paquete que contenga una tarea Flujo de datos independiente para cada tabla de origen que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="6e3d8-136">Para cargar varias tablas mediante varias tareas Flujo de datos en un único paquete</span><span class="sxs-lookup"><span data-stu-id="6e3d8-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="6e3d8-137">Cree un único paquete.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="6e3d8-138">En el flujo de control, utilice una tarea Ejecutar SQL o expresiones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para calcular los extremos.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="6e3d8-139">Para obtener un ejemplo de cómo calcular los puntos de conexión, vea [Especificar un intervalo de datos modificados](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="6e3d8-140">Si es necesario, utilice un contenedor de bucles For para retrasar la ejecución hasta que estén listos los datos modificados para el intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="6e3d8-141">Para obtener un ejemplo de un contenedor de bucles For, vea [Determinar si los datos modificados están preparados](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="6e3d8-142">Use una tarea Script o Ejecutar SQL para ensamblar la instrucción SQL que se usará para consultar si hay cambios.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="6e3d8-143">Para obtener un ejemplo de cómo ensamblar la consulta, vea [Preparar para consultar datos modificados](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="6e3d8-144">Utilice varias tareas Flujo de datos para cargar los datos modificados de cada tabla de origen y aplicarlos al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="6e3d8-145">Configure cada tarea Flujo de datos tal y como se describe en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="6e3d8-146">En cada flujo de datos, utilice un componente de origen para consultar en las tablas de cambios los cambios comprendidos entre los extremos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="6e3d8-147">Para obtener un ejemplo de cómo consultar las tablas de cambios, vea [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="6e3d8-148">Use la transformación División condicional para dirigir las inserciones, las actualizaciones y las eliminaciones a salidas diferentes para procesarlas apropiadamente.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="6e3d8-149">Para obtener un ejemplo de cómo configurar esta transformación para dirigir la salida, vea [Procesar inserciones, actualizaciones y eliminaciones](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="6e3d8-150">Use un componente de destino para aplicar las inserciones al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="6e3d8-151">Use transformaciones Comando de OLE DB con instrucciones UPDATE y DELETE con parámetros para aplicar las actualizaciones y las eliminaciones al destino.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="6e3d8-152">Para obtener un ejemplo de cómo usar esta transformación para aplicar las actualizaciones y eliminaciones, vea [Aplicar los cambios al destino](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  
