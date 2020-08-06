---
title: Ayuda F1 del Asistente para la administración de particiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744670"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="ea331-102">Ayuda F1 del Asistente para la administración de particiones</span><span class="sxs-lookup"><span data-stu-id="ea331-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="ea331-103">Utilice el **Asistente para la administración de particiones** con el fin de administrar y modificar las tablas con particiones existentes a través de la activación de particiones o de la implementación de un escenario de ventanas deslizantes.</span><span class="sxs-lookup"><span data-stu-id="ea331-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="ea331-104">Este asistente puede facilitar la administración de las particiones y simplificar la migración normal de los datos en las tablas.</span><span class="sxs-lookup"><span data-stu-id="ea331-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="ea331-105">Para iniciar el Asistente para la administración de particiones</span><span class="sxs-lookup"><span data-stu-id="ea331-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="ea331-106">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione la base de datos, haga clic con el botón derecho en la tabla en la que quiera crear las particiones, seleccione **Almacenamiento**y haga clic en **Administrar partición**.</span><span class="sxs-lookup"><span data-stu-id="ea331-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="ea331-107">`Note`Si la opción **administrar partición** no está disponible, es posible que haya seleccionado una tabla que no contenga particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="ea331-108">Haga clic en **Crear partición** en el submenú **Almacenamiento** y utilice el **Asistente para la creación de particiones** con el fin de crear las particiones en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ea331-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="ea331-109">Para obtener información general sobre particiones e índices, vea [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ea331-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="ea331-110">En esta sección se proporciona la información necesaria para administrar, modificar e implementar particiones utilizando el **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="ea331-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ea331-111">In This Section</span></span>  
 <span data-ttu-id="ea331-112">En las secciones siguientes se proporciona ayuda de las páginas del **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="ea331-113">Asistente para la administración de particiones (página Seleccionar acción de partición)</span><span class="sxs-lookup"><span data-stu-id="ea331-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="ea331-114">Asistente para administrar particiones (página Activar partición)</span><span class="sxs-lookup"><span data-stu-id="ea331-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="ea331-115">Asistente para administrar particiones (página Desactivar partición)</span><span class="sxs-lookup"><span data-stu-id="ea331-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="ea331-116">Asistente para la administración de particiones (página Seleccionar las opciones de tabla de ensayo)</span><span class="sxs-lookup"><span data-stu-id="ea331-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="ea331-117">Asistente para la administración de particiones (página Seleccionar opción de salida)</span><span class="sxs-lookup"><span data-stu-id="ea331-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="ea331-118">Asistente para la administración de particiones (página Nueva programación de trabajo)</span><span class="sxs-lookup"><span data-stu-id="ea331-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="ea331-119">Asistente para la administración de particiones (página Resumen)</span><span class="sxs-lookup"><span data-stu-id="ea331-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="ea331-120">Asistente para la administración de particiones (página Progreso)</span><span class="sxs-lookup"><span data-stu-id="ea331-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="ea331-121">Página Seleccionar acción de partición</span><span class="sxs-lookup"><span data-stu-id="ea331-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="ea331-122">Utilice la página **Seleccionar acción de partición** para elegir la acción que desee realizar en la partición.</span><span class="sxs-lookup"><span data-stu-id="ea331-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="ea331-123">Crear una tabla de ensayo</span><span class="sxs-lookup"><span data-stu-id="ea331-123">Create a Staging Table</span></span>  
 <span data-ttu-id="ea331-124">La activación y desactivación de particiones es una tarea común de las particiones si tiene una tabla con particiones para la migración de datos de forma regular; por ejemplo, si tiene una tabla con particiones que almacena datos trimestrales actuales y le debe pasar datos nuevos y archivar datos antiguos al final de cada trimestre.</span><span class="sxs-lookup"><span data-stu-id="ea331-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="ea331-125">El asistente diseña la tabla de ensayo con la misma estructura de tablas, columnas y columnas de partición, e índices, y almacena la tabla nueva en el grupo de archivos en los que se encuentra la partición de origen.</span><span class="sxs-lookup"><span data-stu-id="ea331-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="ea331-126">Para crear una tabla de ensayo en la que activar o desactivar las particiones de los datos, seleccione **Crear una tabla de ensayo para la modificación de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="ea331-127">Escenario de ventana deslizante</span><span class="sxs-lookup"><span data-stu-id="ea331-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="ea331-128">Para administrar las particiones en un escenario de ventana deslizante, seleccione **Administrar datos particionados en un escenario de ventana deslizante**.</span><span class="sxs-lookup"><span data-stu-id="ea331-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea331-129">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ea331-129">UI element list</span></span>  
 <span data-ttu-id="ea331-130">**Crear una tabla de ensayo para la modificación de particiones**</span><span class="sxs-lookup"><span data-stu-id="ea331-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="ea331-131">Crea una tabla de ensayo para los datos cuya partición está activando o desactivando en la tabla con particiones existente.</span><span class="sxs-lookup"><span data-stu-id="ea331-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="ea331-132">**Desactivar partición**</span><span class="sxs-lookup"><span data-stu-id="ea331-132">**Switch out partition**</span></span>  
 <span data-ttu-id="ea331-133">Proporciona opciones al quitar una partición de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ea331-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="ea331-134">**Activar partición**</span><span class="sxs-lookup"><span data-stu-id="ea331-134">**Switch in partition**</span></span>  
 <span data-ttu-id="ea331-135">Proporciona opciones al agregar una partición a la tabla.</span><span class="sxs-lookup"><span data-stu-id="ea331-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="ea331-136">**Administrar datos particionados en un escenario de ventana deslizante**</span><span class="sxs-lookup"><span data-stu-id="ea331-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="ea331-137">Anexa una partición vacía a la tabla existente que se puede utilizar para activar la partición de los datos.</span><span class="sxs-lookup"><span data-stu-id="ea331-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="ea331-138">Actualmente, el asistente permite activar la última partición y desactivar la primera.</span><span class="sxs-lookup"><span data-stu-id="ea331-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="ea331-139">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="ea331-140">Página Seleccionar las opciones de activación de la partición</span><span class="sxs-lookup"><span data-stu-id="ea331-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="ea331-141">Use la página **Seleccionar las opciones de activación de la partición** para seleccionar la tabla de ensayo que quiera activar en la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea331-142">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ea331-142">UI element list</span></span>  
 <span data-ttu-id="ea331-143">**Mostrar todas las particiones**</span><span class="sxs-lookup"><span data-stu-id="ea331-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="ea331-144">Seleccione esta opción para mostrar todas las particiones, incluidas las particiones existentes actualmente en la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="ea331-145">**Cuadrícula Partición**</span><span class="sxs-lookup"><span data-stu-id="ea331-145">**Partition grid**</span></span>  
 <span data-ttu-id="ea331-146">Muestra el nombre de la partición, el **Límite izquierdo**, el **Límite derecho**, el **Grupo de archivos**y el **Recuento de filas** de las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ea331-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="ea331-147">**Tabla de activación**</span><span class="sxs-lookup"><span data-stu-id="ea331-147">**Switch in table**</span></span>  
 <span data-ttu-id="ea331-148">Seleccione la tabla de ensayo que contiene la partición que desea agregar a la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="ea331-149">Debe crear esta tabla de almacenamiento provisional antes de activar las particiones con el **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="ea331-150">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="ea331-151">Página Seleccionar las opciones de desactivación de la partición</span><span class="sxs-lookup"><span data-stu-id="ea331-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="ea331-152">Use la página **Seleccionar las opciones de desactivación de la partición** para seleccionar la partición y la tabla de ensayo donde se almacenarán los datos particionados que está desactivando en la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea331-153">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ea331-153">UI element list</span></span>  
 <span data-ttu-id="ea331-154">**Cuadrícula Partición**</span><span class="sxs-lookup"><span data-stu-id="ea331-154">**Partition grid**</span></span>  
 <span data-ttu-id="ea331-155">Muestra el nombre de la partición, el **Límite izquierdo**, el **Límite derecho**, el **Grupo de archivos**y el **Recuento de filas** de las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ea331-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="ea331-156">**Tabla de desactivación**</span><span class="sxs-lookup"><span data-stu-id="ea331-156">**Switch out table**</span></span>  
 <span data-ttu-id="ea331-157">Seleccione una tabla nueva o una tabla existente en la que desea desactivar los datos.</span><span class="sxs-lookup"><span data-stu-id="ea331-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="ea331-158">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="ea331-158">**New**</span></span>  
 <span data-ttu-id="ea331-159">Escriba un nombre nuevo para la tabla de ensayo que desea utilizar para desactivar la partición de la tabla de origen actual.</span><span class="sxs-lookup"><span data-stu-id="ea331-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="ea331-160">**Existente**</span><span class="sxs-lookup"><span data-stu-id="ea331-160">**Existing**</span></span>  
 <span data-ttu-id="ea331-161">Seleccione el nombre de la tabla de ensayo existente que desee utilizar para desactivar la partición de la tabla de origen actual.</span><span class="sxs-lookup"><span data-stu-id="ea331-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="ea331-162">Si la tabla existente contiene datos, estos se sobrescribirán con los datos cuya partición esté desactivando.</span><span class="sxs-lookup"><span data-stu-id="ea331-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="ea331-163">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="ea331-164">Página Seleccionar las opciones de tabla de ensayo</span><span class="sxs-lookup"><span data-stu-id="ea331-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="ea331-165">Utilice la página **Seleccionar las opciones de tabla de ensayo** para crear la tabla de ensayo que desea utilizar para modificar los datos con particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="ea331-166">Las tablas de ensayo deben residir en el mismo grupo de archivos que la partición seleccionada en que se encuentra la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="ea331-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="ea331-167">La tabla de ensayo debe reflejar el diseño tanto de la tabla de origen como de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="ea331-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="ea331-168">También puede crear en la tabla de ensayo los mismos índices que existan en la partición de origen.</span><span class="sxs-lookup"><span data-stu-id="ea331-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="ea331-169">La tabla de ensayo contiene automáticamente una restricción basada en los elementos de la partición de origen.</span><span class="sxs-lookup"><span data-stu-id="ea331-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="ea331-170">Esta restricción se suele generar a partir del valor de límite de la partición de origen.</span><span class="sxs-lookup"><span data-stu-id="ea331-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea331-171">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ea331-171">UI element list</span></span>  
 <span data-ttu-id="ea331-172">**Nombre de tabla de ensayo**</span><span class="sxs-lookup"><span data-stu-id="ea331-172">**Staging table name**</span></span>  
 <span data-ttu-id="ea331-173">Cree un nombre para la tabla de ensayo o acepte el predeterminado que se muestra en el cuadro de edición.</span><span class="sxs-lookup"><span data-stu-id="ea331-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="ea331-174">**Cambiar de partición**</span><span class="sxs-lookup"><span data-stu-id="ea331-174">**Switch partition**</span></span>  
 <span data-ttu-id="ea331-175">Seleccione la partición de origen que desea desactivar de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="ea331-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="ea331-176">**Nuevo valor de límite**</span><span class="sxs-lookup"><span data-stu-id="ea331-176">**New boundary value**</span></span>  
 <span data-ttu-id="ea331-177">Seleccione o escriba el valor de límite que desea para la partición en la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="ea331-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="ea331-178">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="ea331-178">**Filegroup**</span></span>  
 <span data-ttu-id="ea331-179">Seleccione un grupo de archivos para la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="ea331-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="ea331-180">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="ea331-181">Página Seleccionar la opción de salida</span><span class="sxs-lookup"><span data-stu-id="ea331-181">Select Output Option Page</span></span>  
 <span data-ttu-id="ea331-182">Utilice la página **Seleccionar la opción de salida** para especificar cómo desea completar las modificaciones de las particiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="ea331-183">Crear script</span><span class="sxs-lookup"><span data-stu-id="ea331-183">Create Script</span></span>  
 <span data-ttu-id="ea331-184">Cuando el asistente finaliza, crea un script en el Editor de consultas para modificar las particiones en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ea331-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="ea331-185">Seleccione **Crear script** si desea revisar el script y, a continuación, ejecutarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="ea331-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="ea331-186">**Generar script en archivo**</span><span class="sxs-lookup"><span data-stu-id="ea331-186">**Script to file**</span></span>  
 <span data-ttu-id="ea331-187">Permite generar el script en un archivo .sql.</span><span class="sxs-lookup"><span data-stu-id="ea331-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="ea331-188">Especifique **Unicode** o **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="ea331-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="ea331-189">Para especificar el nombre y la ubicación del archivo, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="ea331-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="ea331-190">**Generar script en Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="ea331-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="ea331-191">Guarda el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="ea331-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="ea331-192">**Generar script en la ventana Nueva consulta**</span><span class="sxs-lookup"><span data-stu-id="ea331-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="ea331-193">Genera el script en una ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="ea331-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="ea331-194">Si no hay ninguna ventana del editor abierta, se abre una ventana nueva como destino del script.</span><span class="sxs-lookup"><span data-stu-id="ea331-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="ea331-195">Ejecutar inmediatamente</span><span class="sxs-lookup"><span data-stu-id="ea331-195">Run Immediately</span></span>  
 <span data-ttu-id="ea331-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="ea331-196">**Run immediately**</span></span>  
 <span data-ttu-id="ea331-197">Hace que el asistente finalice las modificaciones en las particiones cuando se hace clic en **Siguiente** o **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ea331-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="ea331-198">Programación</span><span class="sxs-lookup"><span data-stu-id="ea331-198">Schedule</span></span>  
 <span data-ttu-id="ea331-199">Seleccione esta opción para modificar las particiones de la tabla en una fecha y hora programadas.</span><span class="sxs-lookup"><span data-stu-id="ea331-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="ea331-200">**Cambiar programación**</span><span class="sxs-lookup"><span data-stu-id="ea331-200">**Change schedule**</span></span>  
 <span data-ttu-id="ea331-201">Abre el cuadro de diálogo **Nueva programación de trabajo** , donde puede seleccionar, cambiar o ver las propiedades del trabajo programado.</span><span class="sxs-lookup"><span data-stu-id="ea331-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="ea331-202">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="ea331-203">Página Nueva programación del trabajo</span><span class="sxs-lookup"><span data-stu-id="ea331-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="ea331-204">Utilice la página **Nueva programación del trabajo** para ver y cambiar las propiedades de la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="ea331-205">Opciones</span><span class="sxs-lookup"><span data-stu-id="ea331-205">Options</span></span>  
 <span data-ttu-id="ea331-206">Seleccionar el tipo de programación que desea para el trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea331-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="ea331-207">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ea331-207">**Name**</span></span>  
 <span data-ttu-id="ea331-208">Escriba un nuevo nombre de la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="ea331-209">**Trabajos en programación**</span><span class="sxs-lookup"><span data-stu-id="ea331-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="ea331-210">Vea los trabajos existentes que utilizan la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="ea331-211">**Tipo de programación**</span><span class="sxs-lookup"><span data-stu-id="ea331-211">**Schedule type**</span></span>  
 <span data-ttu-id="ea331-212">Seleccione el tipo de programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="ea331-213">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="ea331-213">**Enabled**</span></span>  
 <span data-ttu-id="ea331-214">Habilite o deshabilite la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="ea331-215">Opciones de tipos de programación periódica</span><span class="sxs-lookup"><span data-stu-id="ea331-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="ea331-216">Seleccione la frecuencia del trabajo programado.</span><span class="sxs-lookup"><span data-stu-id="ea331-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="ea331-217">**Sucede**</span><span class="sxs-lookup"><span data-stu-id="ea331-217">**Occurs**</span></span>  
 <span data-ttu-id="ea331-218">Seleccione el intervalo con el que se repite la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="ea331-219">**Se repite cada**</span><span class="sxs-lookup"><span data-stu-id="ea331-219">**Recurs every**</span></span>  
 <span data-ttu-id="ea331-220">Seleccione el número de días o semanas entre las repeticiones de la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="ea331-221">Esta opción no está disponible para las programaciones de periodicidad mensual.</span><span class="sxs-lookup"><span data-stu-id="ea331-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="ea331-222">**Lunes**</span><span class="sxs-lookup"><span data-stu-id="ea331-222">**Monday**</span></span>  
 <span data-ttu-id="ea331-223">Configure el trabajo para que tenga lugar el lunes.</span><span class="sxs-lookup"><span data-stu-id="ea331-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="ea331-224">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-225">**Martes**</span><span class="sxs-lookup"><span data-stu-id="ea331-225">**Tuesday**</span></span>  
 <span data-ttu-id="ea331-226">Configure el trabajo para que tenga lugar el martes.</span><span class="sxs-lookup"><span data-stu-id="ea331-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="ea331-227">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-228">**Miércoles**</span><span class="sxs-lookup"><span data-stu-id="ea331-228">**Wednesday**</span></span>  
 <span data-ttu-id="ea331-229">Configure el trabajo para que tenga lugar el miércoles.</span><span class="sxs-lookup"><span data-stu-id="ea331-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="ea331-230">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-231">**Jueves**</span><span class="sxs-lookup"><span data-stu-id="ea331-231">**Thursday**</span></span>  
 <span data-ttu-id="ea331-232">Configure el trabajo para que tenga lugar el jueves.</span><span class="sxs-lookup"><span data-stu-id="ea331-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="ea331-233">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-234">**Viernes**</span><span class="sxs-lookup"><span data-stu-id="ea331-234">**Friday**</span></span>  
 <span data-ttu-id="ea331-235">Configure el trabajo para que tenga lugar el viernes.</span><span class="sxs-lookup"><span data-stu-id="ea331-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="ea331-236">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-237">**Sábado**</span><span class="sxs-lookup"><span data-stu-id="ea331-237">**Saturday**</span></span>  
 <span data-ttu-id="ea331-238">Configure el trabajo para que tenga lugar el sábado.</span><span class="sxs-lookup"><span data-stu-id="ea331-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="ea331-239">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-240">**Domingo**</span><span class="sxs-lookup"><span data-stu-id="ea331-240">**Sunday**</span></span>  
 <span data-ttu-id="ea331-241">Configure el trabajo para que tenga lugar el domingo.</span><span class="sxs-lookup"><span data-stu-id="ea331-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="ea331-242">Solo está disponible para las programaciones de periodicidad semanal.</span><span class="sxs-lookup"><span data-stu-id="ea331-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="ea331-243">**Day**</span><span class="sxs-lookup"><span data-stu-id="ea331-243">**Day**</span></span>  
 <span data-ttu-id="ea331-244">Seleccione el día del mes en el que se ejecutará la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="ea331-245">Solo está disponible para las programaciones mensuales.</span><span class="sxs-lookup"><span data-stu-id="ea331-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="ea331-246">**de cada**</span><span class="sxs-lookup"><span data-stu-id="ea331-246">**of every**</span></span>  
 <span data-ttu-id="ea331-247">Seleccione el número de meses entre las repeticiones de la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="ea331-248">Solo está disponible para las programaciones mensuales.</span><span class="sxs-lookup"><span data-stu-id="ea331-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="ea331-249">**El**</span><span class="sxs-lookup"><span data-stu-id="ea331-249">**The**</span></span>  
 <span data-ttu-id="ea331-250">Especifique una programación para un día determinado de la semana, en un semana determinada del mes.</span><span class="sxs-lookup"><span data-stu-id="ea331-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="ea331-251">Solo está disponible para las programaciones mensuales.</span><span class="sxs-lookup"><span data-stu-id="ea331-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="ea331-252">**Sucede una vez a las**</span><span class="sxs-lookup"><span data-stu-id="ea331-252">**Occurs once at**</span></span>  
 <span data-ttu-id="ea331-253">Establezca la hora para que el trabajo se produzca diariamente.</span><span class="sxs-lookup"><span data-stu-id="ea331-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="ea331-254">**Sucede cada**</span><span class="sxs-lookup"><span data-stu-id="ea331-254">**Occurs every**</span></span>  
 <span data-ttu-id="ea331-255">Establece el número de horas o minutos entre repeticiones.</span><span class="sxs-lookup"><span data-stu-id="ea331-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="ea331-256">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="ea331-256">**Start date**</span></span>  
 <span data-ttu-id="ea331-257">Establece la fecha en que comienza a ser efectiva esta programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="ea331-258">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="ea331-258">**End date**</span></span>  
 <span data-ttu-id="ea331-259">Establece la fecha en que deja de ser efectiva la programación.</span><span class="sxs-lookup"><span data-stu-id="ea331-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="ea331-260">**Sin fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="ea331-260">**No end date**</span></span>  
 <span data-ttu-id="ea331-261">Especifica que la programación será efectiva indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="ea331-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="ea331-262">Opciones de tipos de programación de una sola vez</span><span class="sxs-lookup"><span data-stu-id="ea331-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="ea331-263">Si programa un trabajo para ejecutarse una vez, debe seleccionar una fecha y hora futuras.</span><span class="sxs-lookup"><span data-stu-id="ea331-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="ea331-264">**Date**</span><span class="sxs-lookup"><span data-stu-id="ea331-264">**Date**</span></span>  
 <span data-ttu-id="ea331-265">Seleccione la fecha de ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea331-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="ea331-266">**Time**</span><span class="sxs-lookup"><span data-stu-id="ea331-266">**Time**</span></span>  
 <span data-ttu-id="ea331-267">Seleccione la hora de ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea331-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="ea331-268">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="ea331-269">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="ea331-269">Summary Page</span></span>  
 <span data-ttu-id="ea331-270">Utilice la página **Resumen** para revisar las opciones que ha seleccionado en las páginas anteriores.</span><span class="sxs-lookup"><span data-stu-id="ea331-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ea331-271">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ea331-271">UI element list</span></span>  
 <span data-ttu-id="ea331-272">**Revisar opciones seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="ea331-272">**Review your selections**</span></span>  
 <span data-ttu-id="ea331-273">Muestra las selecciones que ha realizado en cada página del asistente.</span><span class="sxs-lookup"><span data-stu-id="ea331-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="ea331-274">Haga clic en un nodo para expandir y ver sus opciones seleccionadas previamente.</span><span class="sxs-lookup"><span data-stu-id="ea331-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="ea331-275">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="ea331-276">Página Progreso</span><span class="sxs-lookup"><span data-stu-id="ea331-276">Progress Page</span></span>  
 <span data-ttu-id="ea331-277">Utilice la página **Progreso** para supervisar la información de estado sobre las acciones del **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="ea331-278">Según las opciones que se seleccionen en el asistente, la página **Progreso** puede contener una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="ea331-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="ea331-279">El cuadro superior muestra el estado general del asistente y el número de mensajes de estado, error y advertencia que ha recibido.</span><span class="sxs-lookup"><span data-stu-id="ea331-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="ea331-280">Opciones</span><span class="sxs-lookup"><span data-stu-id="ea331-280">Options</span></span>  
 <span data-ttu-id="ea331-281">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ea331-281">**Details**</span></span>  
 <span data-ttu-id="ea331-282">Proporciona la acción, el estado y los mensajes devueltos por la acción llevada a cabo por el asistente.</span><span class="sxs-lookup"><span data-stu-id="ea331-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="ea331-283">**Acción**</span><span class="sxs-lookup"><span data-stu-id="ea331-283">**Action**</span></span>  
 <span data-ttu-id="ea331-284">Especifica el tipo y el nombre de cada acción.</span><span class="sxs-lookup"><span data-stu-id="ea331-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="ea331-285">**Estado**</span><span class="sxs-lookup"><span data-stu-id="ea331-285">**Status**</span></span>  
 <span data-ttu-id="ea331-286">Indica si la acción del asistente como conjunto ha devuelto el valor **Correcto** o **Error**.</span><span class="sxs-lookup"><span data-stu-id="ea331-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="ea331-287">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="ea331-287">**Message**</span></span>  
 <span data-ttu-id="ea331-288">Proporciona los mensajes de error o de advertencia devueltos por el proceso.</span><span class="sxs-lookup"><span data-stu-id="ea331-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="ea331-289">**Detención**</span><span class="sxs-lookup"><span data-stu-id="ea331-289">**Stop**</span></span>  
 <span data-ttu-id="ea331-290">Detiene la acción llevada a cabo por el asistente.</span><span class="sxs-lookup"><span data-stu-id="ea331-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="ea331-291">**Report**</span><span class="sxs-lookup"><span data-stu-id="ea331-291">**Report**</span></span>  
 <span data-ttu-id="ea331-292">Crea un informe que contiene los resultados del **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="ea331-293">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="ea331-293">The options are:</span></span>  
  
-   <span data-ttu-id="ea331-294">**Ver informe**</span><span class="sxs-lookup"><span data-stu-id="ea331-294">**View Report**</span></span>  
  
-   <span data-ttu-id="ea331-295">**Guardar informe en archivo**</span><span class="sxs-lookup"><span data-stu-id="ea331-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="ea331-296">**Copiar informe al Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="ea331-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="ea331-297">**Enviar informe como correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="ea331-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="ea331-298">**Ver informe**</span><span class="sxs-lookup"><span data-stu-id="ea331-298">**View Report**</span></span>  
 <span data-ttu-id="ea331-299">Abre el cuadro de diálogo **Ver informe** .</span><span class="sxs-lookup"><span data-stu-id="ea331-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="ea331-300">Este cuadro de diálogo contiene un informe de texto con el progreso del **Asistente para la administración de particiones**.</span><span class="sxs-lookup"><span data-stu-id="ea331-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="ea331-301">**Close**</span><span class="sxs-lookup"><span data-stu-id="ea331-301">**Close**</span></span>  
 <span data-ttu-id="ea331-302">Cierra el asistente.</span><span class="sxs-lookup"><span data-stu-id="ea331-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="ea331-303">![Icono de flecha usado con el vínculo Volver al principio](../../2014-toc/media/uparrow16x16.gif "Icono de flecha usado con el vínculo Volver al principio") [En esta sección](#Top)</span><span class="sxs-lookup"><span data-stu-id="ea331-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea331-304">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea331-304">See Also</span></span>  
 [<span data-ttu-id="ea331-305">Tablas e índices con particiones</span><span class="sxs-lookup"><span data-stu-id="ea331-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
