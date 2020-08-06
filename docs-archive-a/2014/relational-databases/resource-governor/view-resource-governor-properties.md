---
title: Ver las propiedades del regulador de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671463"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="7ff3d-102">Ver las propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="7ff3d-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="7ff3d-103">Puede crear o configurar entidades del regulador de recursos, por ejemplo grupos de recursos de servidor y grupos de cargas de trabajo, utilizando la página Propiedades del regulador de recursos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ff3d-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="7ff3d-104">**Antes de empezar:**  [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="7ff3d-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="7ff3d-105">**Visualización de las propiedades del regulador de recursos utilizando lo siguiente:**  [Página Propiedades del regulador de recursos](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="7ff3d-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ff3d-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7ff3d-106">Before You Begin</span></span>  
 <span data-ttu-id="7ff3d-107">Además de ver las propiedades de las entidades del regulador de recursos, puede realizar varias tareas de configuración mediante la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="7ff3d-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="7ff3d-108">Para más información, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ff3d-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="7ff3d-109">Habilitar el regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="7ff3d-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="7ff3d-110">Deshabilitar el regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="7ff3d-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="7ff3d-111">Crear un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="7ff3d-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="7ff3d-112">Crear un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="7ff3d-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="7ff3d-113">Cambiar la configuración del grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="7ff3d-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="7ff3d-114">Cambiar la configuración del grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="7ff3d-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="7ff3d-115">Mover un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="7ff3d-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="7ff3d-116">Cuando haga clic en **Aceptar** después de agregar, eliminar o mover un grupo de cargas de trabajo o un grupo de recursos de servidor, se ejecuta la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="7ff3d-117">Si la operación de creación o cambio de configuración sobre el grupo de recursos de servidor o el grupo de cargas de trabajo produce un error, aparecerá un informe de error debajo del título de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="7ff3d-118">Para ver un mensaje de error más detallado, haga clic en la flecha abajo que aparece en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="7ff3d-119">Es posible determinar si existe una configuración pendiente consultando la vista de administración dinámica [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) para obtener el estado actual de is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ff3d-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="7ff3d-120">Permissions</span></span>  
 <span data-ttu-id="7ff3d-121">Para ver las propiedades del regulador de recursos se requiere el permiso VIEW SERVER STATER.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="7ff3d-122">Las tareas de configuración del regulador de recursos requieren el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="7ff3d-123">Ver la página de propiedades de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="7ff3d-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="7ff3d-124">**Para ver las propiedades del regulador de recursos con la página Propiedades del regulador de recursos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="7ff3d-125">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="7ff3d-126">Haga clic con el botón derecho en **Regulador de recursos** y, luego, haga clic en **Propiedades**. De este modo se abre la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="7ff3d-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="7ff3d-127">Para las obtener descripciones de los campos de la página, vea [Propiedades del regulador de recursos](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="7ff3d-128">Para guardar los cambios, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="7ff3d-129">Propiedades de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="7ff3d-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="7ff3d-130">**Nombre de la función de clasificador**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-130">**Classifier function name**</span></span>  
 <span data-ttu-id="7ff3d-131">Especifique la función clasificadora seleccionándola en la lista.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="7ff3d-132">**Habilitar el regulador de recursos**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="7ff3d-133">Habilite o deshabilite el regulador de recursos seleccionando o desactivando la casilla.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="7ff3d-134">**Grupos de recursos de servidor**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-134">**Resource pools**</span></span>  
 <span data-ttu-id="7ff3d-135">Cree o cambie la configuración del grupo de recursos de servidor utilizando la cuadrícula que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="7ff3d-136">Esta cuadrícula se rellena con información acerca de los grupos internos y predeterminados predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="7ff3d-137">Seleccione un grupo con el que trabajar haciendo clic en la primera columna de la fila para el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="7ff3d-138">Para crear un grupo de recursos, haga clic en la fila que viene precedida por un asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="7ff3d-139">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-139">**Name**</span></span>  
 <span data-ttu-id="7ff3d-140">Especifique el nombre del grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="7ff3d-141">**% de tiempo mínimo de CPU**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="7ff3d-142">Especifique el ancho banda de la CPU promedio garantizado para todas las solicitudes en el grupo de recursos de servidor cuando hay contención de CPU.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="7ff3d-143">El rango es de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="7ff3d-144">**% de tiempo máximo de CPU**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="7ff3d-145">Especifique el promedio máximo de ancho banda de CPU que recibirán todas las solicitudes en este grupo de recursos de servidor cuando hay contención de CPU.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="7ff3d-146">El rango es de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-146">Range is 0 to 100.</span></span> <span data-ttu-id="7ff3d-147">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="7ff3d-148">**% mínimo de memoria**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="7ff3d-149">Especifique la cantidad mínima de memoria reservada para este grupo de recursos de servidor que no se puede compartir con otros grupos de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="7ff3d-150">El rango es de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="7ff3d-151">**% máximo de memoria**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="7ff3d-152">Especifique la memoria total del servidor que puede ser utilizada por las solicitudes en este grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="7ff3d-153">El rango es de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-153">Range is 0 to 100.</span></span> <span data-ttu-id="7ff3d-154">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="7ff3d-155">Para obtener más información, vea [Create Resource POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="7ff3d-156">**Grupos de cargas de trabajo de grupo de recursos de servidor**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="7ff3d-157">Cree o cambie la configuración del grupo de cargas de trabajo utilizando la cuadrícula que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="7ff3d-158">Esta cuadrícula se rellena con información acerca de los grupos internos y predeterminados predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="7ff3d-159">Seleccione un grupo con el que trabajar haciendo clic en la primera columna de la fila para el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="7ff3d-160">Para crear un grupo de cargas de trabajo, haga clic en la fila que viene precedida por un asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="7ff3d-161">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-161">**Name**</span></span>  
 <span data-ttu-id="7ff3d-162">Especifique el nombre del grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="7ff3d-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="7ff3d-163">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-163">**Importance**</span></span>  
 <span data-ttu-id="7ff3d-164">Especifique la importancia relativa de una solicitud en el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="7ff3d-165">Las opciones disponibles son Baja, Media, y Alta.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="7ff3d-166">**Solicitudes máximas**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="7ff3d-167">Especifique el número máximo de solicitudes simultáneas que pueden ejecutarse en el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="7ff3d-168">Debe ser 0 o un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="7ff3d-169">**Tiempo de CPU (seg)**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="7ff3d-170">Especifique la cantidad máxima de tiempo de CPU que una solicitud puede usar.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="7ff3d-171">Debe ser 0 o un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="7ff3d-172">Si es 0, el tiempo es ilimitado.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="7ff3d-173">**% de concesión de memoria**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="7ff3d-174">Especifique la cantidad máxima de memoria que una única solicitud puede tomar del grupo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="7ff3d-175">El rango es de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="7ff3d-176">**Tiempo de espera de concesión (s)**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="7ff3d-177">Especifique el tiempo máximo que una consulta puede esperar hasta que esté disponible un recurso antes de que se produzca un error en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="7ff3d-178">Debe ser 0 o un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="7ff3d-179">**Grado de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="7ff3d-180">Especifique el grado máximo de paralelismo (DOP) para las solicitudes paralelas.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="7ff3d-181">El rango es de 0 a 64.</span><span class="sxs-lookup"><span data-stu-id="7ff3d-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="7ff3d-182">Para obtener más información, vea [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="7ff3d-183">Ver las propiedades del regulador de recursos mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ff3d-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="7ff3d-184">**Ver las propiedades del regulador de recursos mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="7ff3d-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="7ff3d-185">Para ver las definiciones de las entidades del regulador de recursos, use las [Vistas de catálogo del regulador de recursos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="7ff3d-186">Para ver la configuración actual de las entidades del regulador de recursos, use las [Vistas de administración dinámica relacionadas con el regulador de recursos &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ff3d-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff3d-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ff3d-187">See Also</span></span>  
 <span data-ttu-id="7ff3d-188">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="7ff3d-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="7ff3d-189">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="7ff3d-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="7ff3d-190">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7ff3d-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="7ff3d-191">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="7ff3d-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="7ff3d-192">Función clasificadora del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="7ff3d-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
