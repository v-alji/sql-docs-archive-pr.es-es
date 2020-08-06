---
title: Deshabilitar compresión de una tabla o un índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data compression [SQL Server], disabling
ms.assetid: bda1e452-397b-4757-82a4-181217361589
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 80b5775d3b6f7a3f47ab75c5348b556c17b6e676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676000"
---
# <a name="disable-compression-on-a-table-or-index"></a><span data-ttu-id="92667-102">Deshabilitar compresión de una tabla o un índice</span><span class="sxs-lookup"><span data-stu-id="92667-102">Disable Compression on a Table or Index</span></span>
  <span data-ttu-id="92667-103">En este tema se describe cómo deshabilitar la compresión en una tabla o un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92667-103">This topic describes how to disable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92667-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="92667-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92667-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="92667-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92667-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="92667-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="92667-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92667-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92667-108">**Para deshabilitar la compresión a una tabla o un índice, utilice:**</span><span class="sxs-lookup"><span data-stu-id="92667-108">**To disable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="92667-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92667-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="92667-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92667-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92667-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="92667-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="92667-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="92667-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="92667-113">Si la tabla es un montón, la operación de regeneración en modo ONLINE será de un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="92667-113">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="92667-114">Utilice el modo OFFLINE para una operación de regeneración de montón de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="92667-114">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="92667-115">Para obtener más información sobre la compresión de datos, vea [Compresión de datos](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="92667-115">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="92667-116">Para evaluar cómo afecta el cambio del estado de compresión a una tabla, índice o partición, use el procedimiento almacenado [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="92667-116">To evaluate how changing the compression state will affect a table, an index, or a partition, use the [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) stored procedure.</span></span>  
  
-   <span data-ttu-id="92667-117">No se puede cambiar la configuración de compresión de una partición única si la tabla tiene índices no alineados.</span><span class="sxs-lookup"><span data-stu-id="92667-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92667-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92667-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92667-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="92667-119">Permissions</span></span>  
 <span data-ttu-id="92667-120">Requiere el permiso ALTER en la tabla o índice.</span><span class="sxs-lookup"><span data-stu-id="92667-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92667-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92667-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="92667-122">Para deshabilitar la compresión en una tabla</span><span class="sxs-lookup"><span data-stu-id="92667-122">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="92667-123">En el Explorador de objetos, expanda la base de datos que contiene la tabla en la que desea deshabilitar la compresión y después expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="92667-123">In Object Explorer, expand the database that contains the table on which you want to disable compression and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="92667-124">Haga clic con el botón derecho en la tabla o el índice en el que quiera deshabilitar la compresión, seleccione **Almacenamiento** y, luego, **Administrar la compresión...** .</span><span class="sxs-lookup"><span data-stu-id="92667-124">Right-click the table or index on which you want to disable compression, point to **Storage** and select **Manage Compression...**.</span></span>  
  
3.  <span data-ttu-id="92667-125">Para deshabilitar la compresión en un índice, expanda la tabla que contiene el índice y después expanda la carpeta de **Índices** .</span><span class="sxs-lookup"><span data-stu-id="92667-125">To disable compression on an index, expand the table that contains the index and then expand the **Indexes** folder.</span></span>  
  
4.  <span data-ttu-id="92667-126">En la página de bienvenida del **Asistente para compresión de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92667-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="92667-127">En la página de **Seleccionar el tipo de compresión** , seleccione **Ninguno** como el tipo de compresión para aplicar a cada partición del índice en el que desea deshabilitar la compresión.</span><span class="sxs-lookup"><span data-stu-id="92667-127">On the **Select Compression Type** page, select **None** as the compression type to apply to each partition in the index on which you want to disable compression.</span></span> <span data-ttu-id="92667-128">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92667-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="92667-129">Las siguientes opciones están disponibles en la página de **Seleccionar el tipo de compresión** :</span><span class="sxs-lookup"><span data-stu-id="92667-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="92667-130">Casilla**Usar el mismo tipo de compresión para todas las particiones**</span><span class="sxs-lookup"><span data-stu-id="92667-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="92667-131">Active esta casilla para configurar el mismo valor de compresión para todas las particiones.</span><span class="sxs-lookup"><span data-stu-id="92667-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="92667-132">Esto habilita el cuadro de selección y deshabilita la columna **Tipo de compresión** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="92667-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="92667-133">Cuando se activa, las opciones de la lista adyacente son **Ninguna**, **Fila**y **Página**.</span><span class="sxs-lookup"><span data-stu-id="92667-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="92667-134">**Número de partición**</span><span class="sxs-lookup"><span data-stu-id="92667-134">**Partition Number**</span></span>  
     <span data-ttu-id="92667-135">Muestra una lista con cada partición en la tabla o el índice.</span><span class="sxs-lookup"><span data-stu-id="92667-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="92667-136">Esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="92667-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="92667-137">**Tipo de compresión**</span><span class="sxs-lookup"><span data-stu-id="92667-137">**Compression Type**</span></span>  
     <span data-ttu-id="92667-138">Seleccione la opción de compresión para cada partición.</span><span class="sxs-lookup"><span data-stu-id="92667-138">Select the compression option for each partition.</span></span> <span data-ttu-id="92667-139">No estará disponible cuando la casilla **Usar el mismo tipo de compresión para todas las particiones** esté activada.</span><span class="sxs-lookup"><span data-stu-id="92667-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="92667-140">Las opciones son **Ninguna**, **Fila**y **Página**.</span><span class="sxs-lookup"><span data-stu-id="92667-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="92667-141">**Límite**</span><span class="sxs-lookup"><span data-stu-id="92667-141">**Boundary**</span></span>  
     <span data-ttu-id="92667-142">Muestra el límite de la partición.</span><span class="sxs-lookup"><span data-stu-id="92667-142">Displays the partition boundary.</span></span> <span data-ttu-id="92667-143">Esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="92667-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="92667-144">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="92667-144">**Row Count**</span></span>  
     <span data-ttu-id="92667-145">Muestra el número de filas en esta partición.</span><span class="sxs-lookup"><span data-stu-id="92667-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="92667-146">Esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="92667-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="92667-147">**Espacio actual**</span><span class="sxs-lookup"><span data-stu-id="92667-147">**Current Space**</span></span>  
     <span data-ttu-id="92667-148">Muestra el espacio actual que esta partición ocupa en megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="92667-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="92667-149">Esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="92667-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="92667-150">**Espacio comprimido solicitado**</span><span class="sxs-lookup"><span data-stu-id="92667-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="92667-151">Después de hacer clic en **Calcular**, esta columna muestra el tamaño deducido de cada partición después de llevar a cabo la compresión usando la configuración especificada en la columna **Tipo de compresión** .</span><span class="sxs-lookup"><span data-stu-id="92667-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="92667-152">Esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="92667-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="92667-153">**Calcular**</span><span class="sxs-lookup"><span data-stu-id="92667-153">**Calculate**</span></span>  
     <span data-ttu-id="92667-154">Haga clic aquí para deducir el tamaño de cada partición después de realizar la compresión usando la configuración que especificó en la columna **Tipo de compresión** .</span><span class="sxs-lookup"><span data-stu-id="92667-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="92667-155">En la página **Seleccionar la opción de salida** , especifique cómo desea completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="92667-155">In the **Select an Output Option** page, specify how you want to complete this task.</span></span> <span data-ttu-id="92667-156">Seleccione **Crear script** para crear un script SQL basado en las páginas anteriores del asistente.</span><span class="sxs-lookup"><span data-stu-id="92667-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="92667-157">Seleccione **Ejecutar inmediatamente** para crear la nueva tabla con particiones después de completar todas las páginas restantes del asistente.</span><span class="sxs-lookup"><span data-stu-id="92667-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="92667-158">Seleccione **Programar** para crear la tabla con particiones en un momento predeterminado en el futuro.</span><span class="sxs-lookup"><span data-stu-id="92667-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="92667-159">Si selecciona **Crear script**, las opciones siguientes están disponibles debajo de **Opciones de script**:</span><span class="sxs-lookup"><span data-stu-id="92667-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="92667-160">**Generar script en archivo**</span><span class="sxs-lookup"><span data-stu-id="92667-160">**Script to file**</span></span>  
     <span data-ttu-id="92667-161">Genera el script como un archivo .sql.</span><span class="sxs-lookup"><span data-stu-id="92667-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="92667-162">Escriba un nombre de archivo y ubicación en el cuadro de diálogo **Nombre de archivo** o haga clic en **Examinar** para abrir **Ubicación del archivo script** .</span><span class="sxs-lookup"><span data-stu-id="92667-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="92667-163">En **Guardar como**, seleccione **Texto Unicode** o **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="92667-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="92667-164">**Generar script en Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="92667-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="92667-165">Guarda el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="92667-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="92667-166">**Generar script en la ventana Nueva consulta**</span><span class="sxs-lookup"><span data-stu-id="92667-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="92667-167">Genera el script en una nueva ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="92667-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="92667-168">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="92667-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="92667-169">Si selecciona **Programar**, haga clic en **Cambiar programación**.</span><span class="sxs-lookup"><span data-stu-id="92667-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="92667-170">En el cuadro de diálogo **Nueva programación de trabajo**, en el cuadro **Nombre**, escriba el nombre de la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="92667-171">En la lista **Tipo de programación** , seleccione el tipo de la programación:</span><span class="sxs-lookup"><span data-stu-id="92667-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="92667-172">**Iniciar automáticamente al iniciar el Agente SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="92667-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="92667-173">**Iniciar al quedar inactivas las CPU**</span><span class="sxs-lookup"><span data-stu-id="92667-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="92667-174">**Periódica**.</span><span class="sxs-lookup"><span data-stu-id="92667-174">**Recurring**.</span></span> <span data-ttu-id="92667-175">Seleccione esta opción si la nueva tabla con particiones se actualiza con la nueva información de forma regular.</span><span class="sxs-lookup"><span data-stu-id="92667-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="92667-176">**Una vez**.</span><span class="sxs-lookup"><span data-stu-id="92667-176">**One time**.</span></span> <span data-ttu-id="92667-177">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="92667-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="92667-178">Active o desactive la casilla **Habilitado** para habilitar o deshabilitar la programación.</span><span class="sxs-lookup"><span data-stu-id="92667-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="92667-179">Si selecciona **Periódica**:</span><span class="sxs-lookup"><span data-stu-id="92667-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="92667-180">En **Frecuencia**, en la lista **Sucede** , especifique la frecuencia de repetición:</span><span class="sxs-lookup"><span data-stu-id="92667-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="92667-181">Si selecciona **Diario**, en el cuadro **Se repite cada** , escriba la frecuencia con que se repite la programación de trabajo en días.</span><span class="sxs-lookup"><span data-stu-id="92667-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="92667-182">Si selecciona **Semanal**, en el cuadro **Se repite cada** , escriba la frecuencia con que se repite la programación de trabajo en semanas.</span><span class="sxs-lookup"><span data-stu-id="92667-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="92667-183">Seleccione el día o días de la semana en que se ejecuta la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="92667-184">Si selecciona **Mensual**, seleccione **Día** o **El**.</span><span class="sxs-lookup"><span data-stu-id="92667-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="92667-185">Si selecciona **Día**, especifique la fecha del mes que desea que se ejecute la programación de trabajo y con qué frecuencia debe repetirse la programación de trabajo en meses.</span><span class="sxs-lookup"><span data-stu-id="92667-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="92667-186">Por ejemplo, si quiere que la programación de trabajo se ejecute el decimoquinto día de cada mes, seleccione **Día** y escriba "15" en el primer cuadro y "2" en el segundo.</span><span class="sxs-lookup"><span data-stu-id="92667-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="92667-187">Tenga en cuenta que el mayor número permitido en el segundo cuadro es "99".</span><span class="sxs-lookup"><span data-stu-id="92667-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="92667-188">Si selecciona **El**, seleccione el día concreto de la semana del mes en que desea que se ejecute la programación de trabajo y con qué frecuencia debe repetirse la programación de trabajo en meses.</span><span class="sxs-lookup"><span data-stu-id="92667-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="92667-189">Por ejemplo, si quiere que la programación de trabajo se ejecute el último día de la semana de cada mes, seleccione **Día**, seleccione **último** en la primera lista y **día de la semana** en la segunda y, después, escriba "2" en el último cuadro.</span><span class="sxs-lookup"><span data-stu-id="92667-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="92667-190">En las primeras dos listas, también puede seleccionar **primero**, **segundo**, **tercero**o **cuarto**, así como días de la semana concretos (por ejemplo: domingo o miércoles).</span><span class="sxs-lookup"><span data-stu-id="92667-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="92667-191">Tenga en cuenta que el mayor número permitido en el último cuadro es "99".</span><span class="sxs-lookup"><span data-stu-id="92667-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="92667-192">Debajo de **Frecuencia diaria**, especifique la frecuencia con que se repite la programación de trabajo en el día en que se ejecuta:</span><span class="sxs-lookup"><span data-stu-id="92667-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="92667-193">Si selecciona **Sucede una vez a las**, escriba la hora concreta en que debe ejecutarse la programación de trabajo en el cuadro **Sucede una vez a las** .</span><span class="sxs-lookup"><span data-stu-id="92667-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="92667-194">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="92667-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="92667-195">Si selecciona **Sucede cada**, especifique la frecuencia con que se ejecuta la programación de trabajo durante el día seleccionado en **Frecuencia**.</span><span class="sxs-lookup"><span data-stu-id="92667-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="92667-196">Por ejemplo, si quiere que la programación de trabajo se repita cada dos horas al día cuando se ejecuta, seleccione **Sucede cada**, escriba "2" en el primer cuadro y, después, seleccione **horas** en la lista.</span><span class="sxs-lookup"><span data-stu-id="92667-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="92667-197">En esta lista también puede seleccionar **minutos** y **segundos**.</span><span class="sxs-lookup"><span data-stu-id="92667-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="92667-198">Tenga en cuenta que el mayor número permitido en el primer cuadro es "100".</span><span class="sxs-lookup"><span data-stu-id="92667-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="92667-199">En el cuadro **A partir de** , especifique la hora en que la programación de trabajo debe iniciar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="92667-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="92667-200">En el cuadro **Finaliza** , especifique la hora en que la programación de trabajo debe dejar de repetirse.</span><span class="sxs-lookup"><span data-stu-id="92667-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="92667-201">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="92667-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="92667-202">Debajo de **Duración**, en **Fecha de inicio**, escriba la fecha en que desea que la programación de trabajo inicie su ejecución.</span><span class="sxs-lookup"><span data-stu-id="92667-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="92667-203">Seleccione **Fecha de finalización** o **Sin fecha de finalización** para indicar cuándo se debe detener la ejecución de la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="92667-204">Si selecciona **Fecha de finalización**, escriba la fecha en que desea que deje de ejecutarse la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="92667-205">Si selecciona **Una vez**, debajo de **Única repetición**, en el cuadro **Fecha** , escriba la fecha en que se ejecutará la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="92667-206">En el cuadro **Hora** , especifique la hora a la que se ejecutará la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92667-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="92667-207">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="92667-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="92667-208">Debajo de **Resumen**, en **Descripción**, compruebe que todos los valores de la programación de trabajo son correctos.</span><span class="sxs-lookup"><span data-stu-id="92667-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="92667-209">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="92667-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="92667-210">Después de completar esta página, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92667-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="92667-211">En la página **Revisar resumen** , debajo de **Revisar opciones seleccionadas**, expanda todas las opciones disponibles para comprobar que todos los valores son correctos.</span><span class="sxs-lookup"><span data-stu-id="92667-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all settings are correct.</span></span> <span data-ttu-id="92667-212">Si todo está como se esperaba, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="92667-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="92667-213">En la página **Progreso del asistente para compresión** , supervise la información de estado sobre las acciones del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="92667-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="92667-214">Según las opciones que se seleccionen en el asistente, la página de progreso puede contener una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="92667-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="92667-215">El cuadro superior muestra el estado general del asistente y el número de mensajes de estado, error y advertencia que ha recibido.</span><span class="sxs-lookup"><span data-stu-id="92667-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="92667-216">Las siguientes opciones están disponibles en la página **Progreso del asistente para compresión** :</span><span class="sxs-lookup"><span data-stu-id="92667-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="92667-217">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="92667-217">**Details**</span></span>  
     <span data-ttu-id="92667-218">Proporciona la acción, el estado y los mensajes devueltos por la acción llevada a cabo por el asistente.</span><span class="sxs-lookup"><span data-stu-id="92667-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="92667-219">**Acción**</span><span class="sxs-lookup"><span data-stu-id="92667-219">**Action**</span></span>  
     <span data-ttu-id="92667-220">Especifica el tipo y el nombre de cada acción.</span><span class="sxs-lookup"><span data-stu-id="92667-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="92667-221">**Estado**</span><span class="sxs-lookup"><span data-stu-id="92667-221">**Status**</span></span>  
     <span data-ttu-id="92667-222">Indica si la acción del asistente como conjunto ha devuelto el valor **Correcto** o **Error**.</span><span class="sxs-lookup"><span data-stu-id="92667-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="92667-223">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="92667-223">**Message**</span></span>  
     <span data-ttu-id="92667-224">Proporciona los mensajes de error o de advertencia devueltos por el proceso.</span><span class="sxs-lookup"><span data-stu-id="92667-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="92667-225">**Report**</span><span class="sxs-lookup"><span data-stu-id="92667-225">**Report**</span></span>  
     <span data-ttu-id="92667-226">Crea un informe que contiene los resultados del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="92667-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="92667-227">Las opciones son **Ver informe**, **Guardar informe en archivo**, **Copiar informe al Portapapeles**y **Enviar informe como correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="92667-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="92667-228">**Ver informe**</span><span class="sxs-lookup"><span data-stu-id="92667-228">**View Report**</span></span>  
     <span data-ttu-id="92667-229">Abre el cuadro de diálogo **Ver informe** , que contiene un informe de texto del progreso del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="92667-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="92667-230">**Guardar informe en archivo**</span><span class="sxs-lookup"><span data-stu-id="92667-230">**Save Report to File**</span></span>  
     <span data-ttu-id="92667-231">Abre el cuadro de diálogo **Guardar informe como** .</span><span class="sxs-lookup"><span data-stu-id="92667-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="92667-232">**Copiar informe al Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="92667-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="92667-233">Copia los resultados del informe de progreso del asistente al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="92667-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="92667-234">**Enviar informe como correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="92667-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="92667-235">Copia los resultados del informe de progreso del asistente en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="92667-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="92667-236">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="92667-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92667-237">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92667-237">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="92667-238">Para deshabilitar la compresión en una tabla</span><span class="sxs-lookup"><span data-stu-id="92667-238">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="92667-239">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92667-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92667-240">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="92667-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92667-241">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92667-241">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Person.Person REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
#### <a name="to-disable-compression-on-an-index"></a><span data-ttu-id="92667-242">Para deshabilitar la compresión en un índice</span><span class="sxs-lookup"><span data-stu-id="92667-242">To disable compression on an index</span></span>  
  
1.  <span data-ttu-id="92667-243">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92667-243">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92667-244">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="92667-244">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92667-245">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="92667-245">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Person_rowguid ON Person.Person REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
 <span data-ttu-id="92667-246">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) y [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92667-246">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
