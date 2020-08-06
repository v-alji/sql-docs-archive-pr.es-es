---
title: Creación de un plan de mantenimiento (superficie de diseño del plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675354"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="5d1c6-102">Crear un plan de mantenimiento (superficie de diseño del plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="5d1c6-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="5d1c6-103">En este tema se describe cómo crear un plan de mantenimiento de varios servidores o de uno mediante la superficie de diseño del plan de mantenimiento de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d1c6-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5d1c6-104">Aunque el **Asistente para plan de mantenimiento** es mejor para crear planes de mantenimiento básicos, crear un plan con la superficie de diseño le permite usar un flujo de trabajo mejorado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="5d1c6-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d1c6-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d1c6-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5d1c6-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5d1c6-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5d1c6-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="5d1c6-109">Crear un plan de mantenimiento mediante la superficie de diseño del plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5d1c6-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d1c6-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5d1c6-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5d1c6-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5d1c6-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5d1c6-112">Para crear un plan de mantenimiento multiservidor, se debe configurar un entorno multiservidor que contenga un servidor maestro y uno o varios servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="5d1c6-113">Los planes de mantenimiento multiservidor se deben crear y mantener en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="5d1c6-114">Estos planes se pueden ver, pero no mantener, en servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="5d1c6-115">Los miembros de los roles **db_ssisadmin** y **dc_admin** quizá puedan elevar sus privilegios a **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="5d1c6-116">Esta elevación de privilegio se puede producir porque estos roles pueden modificar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ; estos paquetes los puede ejecutar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando el contexto de seguridad de **sysadmin** del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="5d1c6-117">Para protegerse contra esta elevación de privilegio al ejecutar planes de mantenimiento, conjuntos de recopilación de datos y otros paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configure los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ejecutan paquetes para usar una cuenta de proxy con privilegios limitados o agregar solo los miembros de **sysadmin** a los roles **db_ssisadmin** y **dc_admin** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d1c6-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5d1c6-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d1c6-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="5d1c6-119">Permissions</span></span>  
 <span data-ttu-id="5d1c6-120">Para crear o administrar planes de mantenimiento, debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="5d1c6-121">El Explorador de objetos solo muestra el nodo **Planes de mantenimiento** para los usuarios que son miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d1c6-122">Usar la Superficie de diseño del plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5d1c6-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="5d1c6-123">Para crear un plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5d1c6-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="5d1c6-124">En el Explorador de objetos, haga clic en el signo más para expandir el servidor donde desea crear un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="5d1c6-125">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="5d1c6-126">Haga clic con el botón derecho en la carpeta **Planes de mantenimiento** y seleccione **Nuevo plan de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="5d1c6-127">En el cuadro de diálogo **Nuevo plan de mantenimiento** , en el cuadro **Nombre** , escriba un nombre para el plan y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="5d1c6-128">De este modo se abre el cuadro de herramientas y la superficie _maintenance_plan_name_ **[Design]** con el subplán **Subplan_1** creado en la cuadrícula principal.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="5d1c6-129">Las siguientes opciones están disponibles en el encabezado del espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="5d1c6-130">**Agregar subplán**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-130">**Add Subplan**</span></span>  
     <span data-ttu-id="5d1c6-131">Agrega un subplán que puede configurar.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="5d1c6-132">**Propiedades del subplán**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="5d1c6-133">Muestra el cuadro de diálogo **Propiedades del subplán** para el subplán seleccionado en la cuadrícula principal.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="5d1c6-134">O bien, haga doble clic en un subplán de la cuadrícula para mostrar el cuadro de diálogo **Propiedades del subplán** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="5d1c6-135">Vea a continuación para obtener más información sobre este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-136">**Eliminar subplán seleccionado**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="5d1c6-137">Elimina el subplán seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-138">**Programación del subplán**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="5d1c6-139">Muestra el cuadro de diálogo **Nueva programación de trabajo** para el subplán seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-140">**Quitar programación**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="5d1c6-141">Quita una programación del subplán seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-142">**Administrar conexiones**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-142">**Manage Connections**</span></span>  
     <span data-ttu-id="5d1c6-143">Muestra el cuadro de diálogo **Administrar conexiones** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="5d1c6-144">Se utiliza para agregar conexiones adicionales de instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="5d1c6-145">Vea a continuación para obtener más información sobre este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-146">**Informes y registro**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="5d1c6-147">Muestra el cuadro de diálogo **Informes y registro** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="5d1c6-148">Vea a continuación para obtener más información sobre este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-149">**Servidores**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-149">**Servers**</span></span>  
     <span data-ttu-id="5d1c6-150">Muestra el cuadro de diálogo **Servidores** , que se usa para seleccionar los servidores en los que se ejecutarán las tareas del subplan.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="5d1c6-151">Esta opción está habilitada solo en servidores maestros en entornos multiservidor.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="5d1c6-152">Para obtener más información, vea [Crear un entorno multiservidor](../../ssms/agent/create-a-multiserver-environment.md) y [Maintenance Plan &#40;Servers&#41; (Plan de mantenimiento &#40;servidores&#41;)](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="5d1c6-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="5d1c6-153">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-153">**Name**</span></span>  
     <span data-ttu-id="5d1c6-154">Muestra el nombre del plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-154">Display the maintenance plan name.</span></span> <span data-ttu-id="5d1c6-155">En los nuevos planes de mantenimiento, el nombre se especifica en un cuadro de diálogo antes de que se abra el diseñador de planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="5d1c6-156">Para cambiar el nombre de un plan de mantenimiento, haga clic con el botón derecho en el plan en el Explorador de objetos y, luego, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="5d1c6-157">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-157">**Description**</span></span>  
     <span data-ttu-id="5d1c6-158">Vea o especifique una descripción para el plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="5d1c6-159">La longitud máxima de una descripción es de 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="5d1c6-160">**Superficie del diseñador**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-160">**Designer Surface**</span></span>  
     <span data-ttu-id="5d1c6-161">Diseña y mantiene los planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="5d1c6-162">Utilice la superficie del diseñador para agregar o eliminar tareas de mantenimiento a un plan, especificar los vínculos de precedencia entre las tareas e indicar la bifurcación y el paralelismo de tareas.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="5d1c6-163">Un vínculo de precedencia entre dos tareas establece una relación entre ellas.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="5d1c6-164">La segunda tarea (la *tarea dependiente*) solo se ejecuta si el resultado de la ejecución de la primera tarea (la *tarea precedente*) coincide con el criterio especificado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="5d1c6-165">Por lo general, el resultado de la ejecución es **Correcto**, **Error**o **Conclusión**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="5d1c6-166">Para obtener más información, vea el paso **8** a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="5d1c6-167">En el encabezado del espacio de diseño, haga doble clic en **Subplan_1** y escriba un nombre y una descripción para el subplán en el cuadro de diálogo **Propiedades del subplán** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-168">Las siguientes opciones están disponibles en el cuadro de diálogo **Propiedades del subplán** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-169">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-169">**Name**</span></span>  
     <span data-ttu-id="5d1c6-170">Nombre del subplán.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-171">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-171">**Description**</span></span>  
     <span data-ttu-id="5d1c6-172">Breve descripción del subplán.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-173">**Programación**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-173">**Schedule**</span></span>  
     <span data-ttu-id="5d1c6-174">Indica en qué programación se ejecutó el subplán.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="5d1c6-175">Haga clic en **Programación del subplán** para abrir el cuadro de diálogo **Nueva programación de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="5d1c6-176">Haga clic en **Quitar programación** para eliminar la programación del subplán.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="5d1c6-177">Lista de**Ejecutar como**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-177">**Run as** list</span></span>  
     <span data-ttu-id="5d1c6-178">Seleccione la cuenta que se utilizará para ejecutar esta subtarea.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="5d1c6-179">Haga clic en **Programación del subplán** para escribir detalles de programación en el cuadro de diálogo **Nueva programación del trabajo** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="5d1c6-180">Para generar el subplán, arrastre y coloque los elementos del flujo de tareas del **Cuadro de herramientas** a la superficie de diseño del plan.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="5d1c6-181">Haga doble clic en las tareas para abrir los cuadros de diálogo que le permitirán configurar las opciones de las tareas.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="5d1c6-182">Las siguientes tareas del plan de mantenimiento están disponibles en **Cuadro de herramientas**:</span><span class="sxs-lookup"><span data-stu-id="5d1c6-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="5d1c6-183">**Tarea Copia de seguridad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-184">**Tarea Comprobar la integridad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-185">**Tarea Ejecutar trabajo del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-186">**Tarea Ejecutar instrucción T-SQL**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-187">**Tarea Limpieza de historial**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-188">**Tarea Limpieza de mantenimiento**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-189">**Tarea Notificar al operador**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-190">**Tarea Volver a generar índice**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-191">**Tarea Reorganizar índice**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-192">**Tarea Reducir base de datos**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="5d1c6-193">**Tarea Actualizar estadísticas**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="5d1c6-194">Para agregar tareas al **Cuadro de herramientas**:</span><span class="sxs-lookup"><span data-stu-id="5d1c6-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="5d1c6-195">En el menú **Herramientas** , haga clic en **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="5d1c6-196">Seleccione las herramientas que desee que aparezcan en el **Cuadro de herramientas**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5d1c6-197">Agregar tareas del plan de mantenimiento al **Cuadro de herramientas** también hace que estén disponibles en el **Asistente para planes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="5d1c6-198">Para obtener más información sobre las tareas individuales anteriores, vea [Using Maintenance Plan Wizard (Usar el Asistente para planes de mantenimiento)](use-the-maintenance-plan-wizard.md#SSMSProcedure) en **Start the Maintenance Plan Wizard (Iniciar el Asistente para planes de mantenimiento)** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="5d1c6-199">Para definir un flujo de trabajo entre tareas:</span><span class="sxs-lookup"><span data-stu-id="5d1c6-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="5d1c6-200">Haga clic con el botón derecho en la tarea anterior y seleccione **Agregar restricción de precedencia**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="5d1c6-201">En el cuadro de diálogo **Flujo de control** , en la lista **Para** , seleccione la tarea dependiente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="5d1c6-202">Haga doble clic en el conector entre las dos tareas para abrir el cuadro de diálogo **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="5d1c6-203">Las siguientes opciones están disponibles en el cuadro de diálogo **Editor de restricciones de precedencia** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="5d1c6-204">**Opción de restricción**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-204">**Constraint option**</span></span>  
         <span data-ttu-id="5d1c6-205">Define cómo funciona una restricción entre dos tareas.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="5d1c6-206">Lista**Operación de evaluación**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="5d1c6-207">Permite especificar la operación de evaluación que utiliza la restricción de precedencia.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="5d1c6-208">Las operaciones son: **Restricción**, **Expresión**, **Expresión y restricción** y **Expresión o restricción**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="5d1c6-209">Lista**Valor**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-209">**Value** list</span></span>  
         <span data-ttu-id="5d1c6-210">Especifique el valor de restricción: **Correcto**, **Error** o **Finalización**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="5d1c6-211">**Correcto** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5d1c6-212">La línea de restricción de precedencia es verde para **Correcto**, roja para **Error**y azul para **Conclusión**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="5d1c6-213">**Expression**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-213">**Expression**</span></span>  
         <span data-ttu-id="5d1c6-214">Si usa las operaciones **Expresión**, **Expresión y restricción**o **Expresión o restricción**, escriba una expresión.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="5d1c6-215">La expresión debe evaluarse como un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="5d1c6-216">**Test**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-216">**Test**</span></span>  
         <span data-ttu-id="5d1c6-217">Permite validar la expresión.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="5d1c6-218">**Varias restricciones**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="5d1c6-219">Define el modo en que varias restricciones interoperan para controlar la ejecución de la tarea restringida.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="5d1c6-220">**Y lógico**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-220">**Logical AND**</span></span>  
         <span data-ttu-id="5d1c6-221">Seleccione esta opción para indicar que varias restricciones de precedencia en el mismo archivo ejecutable deben evaluarse de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="5d1c6-222">Todas las restricciones deben evaluarse como True.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="5d1c6-223">Es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5d1c6-224">Este tipo de restricción de precedencia se muestra como una línea sólida verde, roja o azul.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="5d1c6-225">**O lógico**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-225">**Logical OR**</span></span>  
         <span data-ttu-id="5d1c6-226">Seleccione esta opción para indicar que varias restricciones de precedencia en el mismo archivo ejecutable deben evaluarse de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="5d1c6-227">Al menos una restricción debe evaluarse como True.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5d1c6-228">Este tipo de restricción de precedencia se muestra como una línea de puntos verde, roja o azul.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="5d1c6-229">Para agregar otro subplán que contiene tareas que se ejecutan en otra programación, haga clic en **Agregar subplán** en la barra de herramientas para abrir el cuadro de diálogo **Propiedades del subplán** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="5d1c6-230">Para agregar conexiones a servidores diferentes:</span><span class="sxs-lookup"><span data-stu-id="5d1c6-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="5d1c6-231">En la barra de herramientas del espacio de diseño, haga clic en **Administrar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="5d1c6-232">En el cuadro de diálogo **Administrar conexiones** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="5d1c6-233">En el cuadro de diálogo **Propiedades de conexión** , en el cuadro **Nombre de la conexión** , escriba el nombre de la conexión que va a crear.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="5d1c6-234">En **Especificar lo siguiente para conectarse a los datos de SQL Server**, en el cuadro **Seleccionar o especificar un nombre de servidor**, escriba el nombre del servidor SQL Server que quiere usar o haga clic en los puntos suspensivos **(...)** y seleccione un servidor en el cuadro de diálogo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="5d1c6-235">Si selecciona un servidor en el cuadro de diálogo **SQL Server** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5d1c6-236">En **Especificar información para iniciar sesión en el servidor**, seleccione **Usar seguridad integrada de Windows NT** o **Usar un nombre de usuario y contraseña específicos**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="5d1c6-237">Si elige usar un nombre de usuario y una contraseña específicos, escriba esa información en los cuadros **Nombre de usuario** y **Contraseña** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="5d1c6-238">En el cuadro de diálogo **Propiedades de conexión** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="5d1c6-239">En el cuadro de diálogo **Administrar las conexiones** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="5d1c6-240">Para especificar las opciones de informes:</span><span class="sxs-lookup"><span data-stu-id="5d1c6-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="5d1c6-241">En la barra de herramientas del espacio de diseño, haga clic en **Informes y registro**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="5d1c6-242">En el cuadro de diálogo **Informes y registro** , debajo de **Informes**, seleccione **Generar un informe de archivo de texto** o **Enviar informe a un destinatario de correo electrónico** o ambos.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="5d1c6-243">Si selecciona **Generar un informe de archivo de texto**, seleccione **Crear un nuevo archivo** o **Anexar a archivo**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="5d1c6-244">Según la selección anterior, escriba el nombre y la ruta de acceso completa del nuevo archivo o del archivo que se va a anexar especificando la información en los cuadros **Carpeta** o **Nombre de archivo** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="5d1c6-245">Como alternativa, haga clic en los puntos suspensivos **(...)** y seleccione la ruta de acceso a la carpeta o el nombre de archivo en los cuadros de diálogo **Buscar carpeta-**_SERVER_NAME_ o **buscar archivos de base de datos-**_SERVER_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="5d1c6-246">Si selecciona **Enviar informe a un destinatario de correo electrónico**, en la lista de **Operador del agente** , seleccione el destinatario del informe enviado por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="5d1c6-247">El Agente SQL Server debe configurarse para que utilice el Correo electrónico de base de datos para enviar correo.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="5d1c6-248">Para obtener más información, consulte [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="5d1c6-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="5d1c6-249">Para guardar más información detallada, en **Registro**, seleccione **Registrar información adicional**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="5d1c6-250">Para escribir la información de los resultados del plan de mantenimiento para otro servidor, seleccione **Registrar en el servidor remoto** y después seleccione una conexión al servidor en la lista **Conexión** o haga clic en **Nueva** y escriba la información de conexión en el cuadro de diálogo **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="5d1c6-251">En el cuadro de diálogo **Informes y registro** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="5d1c6-252">Para ver los resultados en el visor del archivo de registro, en el **Explorador de objetos**, haga clic con el botón derecho en la carpeta **Planes de mantenimiento** o en el plan de mantenimiento específico y, luego, selecciones **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="5d1c6-253">Las siguientes opciones están disponibles en el cuadro de diálogo **visor del archivo de registros-**_SERVER_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="5d1c6-254">**Cargar registro**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-254">**Load Log**</span></span>  
     <span data-ttu-id="5d1c6-255">Abre un cuadro de diálogo donde puede especificar un archivo de registro para cargar.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="5d1c6-256">**Exportarar**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-256">**Export**</span></span>  
     <span data-ttu-id="5d1c6-257">Abre un cuadro de diálogo que permite exportar la información que se muestra en la cuadrícula **Resumen de archivos de registro** a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="5d1c6-258">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-258">**Refresh**</span></span>  
     <span data-ttu-id="5d1c6-259">Actualice la vista de los registros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="5d1c6-260">El botón **Actualizar** hace que se vuelvan a leer los registros seleccionados del servidor de destino al tiempo que se aplica una configuración de filtro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="5d1c6-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-261">**Filter**</span></span>  
     <span data-ttu-id="5d1c6-262">Abre un cuadro de diálogo que permite especificar la configuración que se usa para filtrar el archivo de registro, como **Conexión**, **Fecha**u otros criterios de filtro de **General** .</span><span class="sxs-lookup"><span data-stu-id="5d1c6-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="5d1c6-263">**Búsqueda**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-263">**Search**</span></span>  
     <span data-ttu-id="5d1c6-264">Permite buscar texto específico en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-264">Search the log file for specific text.</span></span> <span data-ttu-id="5d1c6-265">No se admite la búsqueda con caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="5d1c6-266">**Detención**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-266">**Stop**</span></span>  
     <span data-ttu-id="5d1c6-267">Detiene la carga de las entradas del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-267">Stops loading the log file entries.</span></span> <span data-ttu-id="5d1c6-268">Por ejemplo, puede utilizar esta opción si la carga de un archivo de registro remoto o sin conexión tarda mucho tiempo y solo desea ver las entradas más recientes.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="5d1c6-269">**Resumen de archivos de registro**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-269">**Log file summary**</span></span>  
     <span data-ttu-id="5d1c6-270">Este panel de información muestra un resumen del filtro del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="5d1c6-271">Si no se ha filtrado el archivo, se mostrará el siguiente texto: **No se aplicó ningún filtro**.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="5d1c6-272">Si se aplicó un filtro al registro, se mostrará el texto **Filtrar entradas del registro en:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="5d1c6-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-273">**Date**</span></span>  
     <span data-ttu-id="5d1c6-274">Muestra la fecha del evento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="5d1c6-275">**Origen**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-275">**Source**</span></span>  
     <span data-ttu-id="5d1c6-276">Muestra la característica de origen desde la que se crea el evento, como el nombre del servicio (MSSQLSERVER, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="5d1c6-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="5d1c6-277">No aparece para todos los tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="5d1c6-278">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-278">**Message**</span></span>  
     <span data-ttu-id="5d1c6-279">Muestra todos los mensajes asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="5d1c6-280">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-280">**Log Type**</span></span>  
     <span data-ttu-id="5d1c6-281">Muestra el tipo de registro al que pertenece el evento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="5d1c6-282">Todos los registros seleccionados aparecen en la ventana de resumen del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="5d1c6-283">**Origen del registro**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-283">**Log Source**</span></span>  
     <span data-ttu-id="5d1c6-284">Muestra una descripción del registro de origen en el que se captura el evento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="5d1c6-285">**Detalles de las filas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-285">**Selected row details**</span></span>  
     <span data-ttu-id="5d1c6-286">Seleccione una fila para mostrar detalles adicionales sobre la fila de evento seleccionada en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="5d1c6-287">Puede ordenar de nuevo las columnas arrastrándolas a nuevas ubicaciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="5d1c6-288">Puede modificar el tamaño de las columnas arrastrando las barras de separación de las columnas del encabezado de la cuadrícula hacia la izquierda o hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="5d1c6-289">Haga doble clic en las barras de separación de las columnas del encabezado de la cuadrícula para ajustar automáticamente el tamaño de la columna al ancho del contenido.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="5d1c6-290">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="5d1c6-290">**Instance**</span></span>  
     <span data-ttu-id="5d1c6-291">Nombre de la instancia en que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="5d1c6-292">Esto se muestra como *nombre de equipo*\\*nombre de instancia*.</span><span class="sxs-lookup"><span data-stu-id="5d1c6-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
