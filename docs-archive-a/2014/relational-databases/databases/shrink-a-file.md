---
title: Reducir un archivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744122"
---
# <a name="shrink-a-file"></a><span data-ttu-id="c21ca-102">Reducir un archivo</span><span class="sxs-lookup"><span data-stu-id="c21ca-102">Shrink a File</span></span>
  <span data-ttu-id="c21ca-103">En este tema se describe cómo reducir un archivo de datos o de registro en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c21ca-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c21ca-104">La reducción de los archivos de datos permite recuperar espacio moviendo páginas de datos del final del archivo a espacio desocupado próximo al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="c21ca-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="c21ca-105">Cuando se crea suficiente espacio disponible al final del archivo, las páginas de datos situadas al final del mismo se pueden desasignar y devolver al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="c21ca-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="c21ca-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c21ca-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c21ca-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c21ca-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c21ca-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c21ca-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c21ca-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c21ca-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c21ca-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c21ca-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c21ca-111">**Para reducir un archivo de datos o de registro, use:**</span><span class="sxs-lookup"><span data-stu-id="c21ca-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="c21ca-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c21ca-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c21ca-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c21ca-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c21ca-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c21ca-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c21ca-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c21ca-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c21ca-116">El archivo de datos principal no puede reducirse a un tamaño menor que el del archivo principal de la base de datos model.</span><span class="sxs-lookup"><span data-stu-id="c21ca-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c21ca-117">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c21ca-117">Recommendations</span></span>  
  
-   <span data-ttu-id="c21ca-118">Los datos que se mueven para reducir un archivo se pueden dispersar en cualquier ubicación disponible en el archivo.</span><span class="sxs-lookup"><span data-stu-id="c21ca-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="c21ca-119">Esto produce la fragmentación de índices y puede reducir el rendimiento de las consultas que buscan un intervalo del índice.</span><span class="sxs-lookup"><span data-stu-id="c21ca-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="c21ca-120">Para eliminar la fragmentación, considere la posibilidad de volver a generar los índices en el archivo después de la reducción.</span><span class="sxs-lookup"><span data-stu-id="c21ca-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c21ca-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c21ca-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c21ca-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="c21ca-122">Permissions</span></span>  
 <span data-ttu-id="c21ca-123">Debe pertenecer al rol fijo de servidor **sysadmin** o al rol fijo de base de datos **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c21ca-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c21ca-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="c21ca-125">Para reducir un archivo de datos o de registro</span><span class="sxs-lookup"><span data-stu-id="c21ca-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="c21ca-126">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="c21ca-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c21ca-127">Expanda **Bases de datos** y, después, haga clic con el botón derecho en la base de datos que quiera reducir.</span><span class="sxs-lookup"><span data-stu-id="c21ca-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="c21ca-128">Seleccione **Tareas**y **Reducir**y haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="c21ca-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="c21ca-129">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="c21ca-129">**Database**</span></span>  
     <span data-ttu-id="c21ca-130">Muestra el nombre de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c21ca-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="c21ca-131">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="c21ca-131">**File type**</span></span>  
     <span data-ttu-id="c21ca-132">Seleccione el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="c21ca-132">Select the file type for the file.</span></span> <span data-ttu-id="c21ca-133">Las opciones disponibles son **Datos** y **Registro** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="c21ca-134">El valor predeterminado es **Datos**.</span><span class="sxs-lookup"><span data-stu-id="c21ca-134">The default selection is **Data**.</span></span> <span data-ttu-id="c21ca-135">Si se selecciona un tipo de grupo de archivos diferente, la selección de los demás campos también cambia.</span><span class="sxs-lookup"><span data-stu-id="c21ca-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="c21ca-136">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="c21ca-136">**Filegroup**</span></span>  
     <span data-ttu-id="c21ca-137">Seleccione un grupo de archivos en la lista de grupos de archivos asociados al **Tipo de archivo** seleccionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c21ca-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="c21ca-138">Si se selecciona un grupo de archivos diferente, la selección de los demás campos también cambia.</span><span class="sxs-lookup"><span data-stu-id="c21ca-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="c21ca-139">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="c21ca-139">**File name**</span></span>  
     <span data-ttu-id="c21ca-140">Elija un archivo en la lista de archivos disponibles del grupo de archivos y del tipo de archivo seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c21ca-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="c21ca-141">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="c21ca-141">**Location**</span></span>  
     <span data-ttu-id="c21ca-142">Muestra la ruta de acceso completa al archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c21ca-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="c21ca-143">La ruta no se puede editar, pero se puede copiar al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="c21ca-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="c21ca-144">**Espacio asignado actualmente**</span><span class="sxs-lookup"><span data-stu-id="c21ca-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="c21ca-145">Para los archivos de datos, muestra el espacio asignado actualmente.</span><span class="sxs-lookup"><span data-stu-id="c21ca-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="c21ca-146">En los archivos de registro, muestra el espacio asignado, calculado a partir del resultado de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="c21ca-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="c21ca-147">**Espacio disponible**</span><span class="sxs-lookup"><span data-stu-id="c21ca-147">**Available free space**</span></span>  
     <span data-ttu-id="c21ca-148">En los archivos de datos, muestra el espacio disponible, calculado a partir del resultado de DBCC SHOWFILESTATS(fileid).</span><span class="sxs-lookup"><span data-stu-id="c21ca-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="c21ca-149">En los archivos de registro, muestra el espacio disponible, calculado a partir del resultado de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="c21ca-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="c21ca-150">**Liberar espacio no utilizado**</span><span class="sxs-lookup"><span data-stu-id="c21ca-150">**Release unused space**</span></span>  
     <span data-ttu-id="c21ca-151">Hace que se libere el espacio no utilizado de los archivos para el sistema operativo y reduce el archivo a la última extensión asignada, lo que disminuye el tamaño del archivo sin mover los datos.</span><span class="sxs-lookup"><span data-stu-id="c21ca-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="c21ca-152">No se realiza ningún intento de reubicación de las filas en páginas no asignadas.</span><span class="sxs-lookup"><span data-stu-id="c21ca-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="c21ca-153">**Reorganizar páginas antes de liberar espacio no utilizado**</span><span class="sxs-lookup"><span data-stu-id="c21ca-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="c21ca-154">Equivale a ejecutar DBCC SHRINKFILE con la especificación del tamaño del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="c21ca-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="c21ca-155">Si se selecciona esta opción, el usuario debe especificar el tamaño del archivo de destino en el cuadro **Reducir el archivo a** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="c21ca-156">**Reducir el archivo a**</span><span class="sxs-lookup"><span data-stu-id="c21ca-156">**Shrink file to**</span></span>  
     <span data-ttu-id="c21ca-157">Especifica el tamaño del archivo de destino para la operación de reducción.</span><span class="sxs-lookup"><span data-stu-id="c21ca-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="c21ca-158">El tamaño no puede ser inferior al espacio asignado actual ni superior a la extensión total asignada al archivo.</span><span class="sxs-lookup"><span data-stu-id="c21ca-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="c21ca-159">Si se introduce un valor inferior al mínimo o superior al máximo, se restablecerá el valor mínimo o máximo cuando cambie el foco o cuando se haga clic en los botones de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c21ca-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="c21ca-160">**Vaciar el archivo migrando los datos a otros archivos del mismo grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="c21ca-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="c21ca-161">Migra todos los datos del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c21ca-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="c21ca-162">Esta opción permite que el archivo se pueda quitar mediante la instrucción ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c21ca-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="c21ca-163">Esta opción equivale a ejecutar DBCC SHRINKFILE con la opción EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="c21ca-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="c21ca-164">Seleccione el tipo y el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="c21ca-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="c21ca-165">También puede activar la casilla **Liberar espacio no utilizado** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="c21ca-166">Si activa esta opción, el espacio no utilizado del archivo se libera al sistema operativo y el archivo se reduce a la última extensión asignada.</span><span class="sxs-lookup"><span data-stu-id="c21ca-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="c21ca-167">De esta forma, se reduce el tamaño del archivo sin necesidad de mover datos.</span><span class="sxs-lookup"><span data-stu-id="c21ca-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="c21ca-168">También puede seleccionar la casilla **Reorganizar archivos antes de liberar espacio no utilizado** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="c21ca-169">Si activa esta opción, debe especificar el valor **Reducir el archivo a** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="c21ca-170">De forma predeterminada, esta opción no está activada.</span><span class="sxs-lookup"><span data-stu-id="c21ca-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="c21ca-171">Si activa esta opción, el espacio no utilizado del archivo se libera al sistema operativo y se intentan reubicar las filas en páginas no asignadas.</span><span class="sxs-lookup"><span data-stu-id="c21ca-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="c21ca-172">De manera opcional, especifique el porcentaje máximo de espacio disponible que desee dejar en el archivo de la base de datos después de reducirla.</span><span class="sxs-lookup"><span data-stu-id="c21ca-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="c21ca-173">Los valores válidos están comprendidos entre 0 y 99.</span><span class="sxs-lookup"><span data-stu-id="c21ca-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="c21ca-174">Esta opción solo está disponible cuando la opción **Reorganizar archivos antes de liberar espacio no utilizado** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="c21ca-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="c21ca-175">De manera opcional, active la casilla **Vaciar el archivo migrando los datos a otros archivos del mismo grupo de archivos** .</span><span class="sxs-lookup"><span data-stu-id="c21ca-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="c21ca-176">Si activa esta opción, los datos se mueven del archivo especificado a otros archivos del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="c21ca-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="c21ca-177">A continuación, el archivo vacío puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="c21ca-177">The empty file can then be deleted.</span></span> <span data-ttu-id="c21ca-178">Esta opción equivale a ejecutar DBCC SHRINKFILE con la opción EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="c21ca-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="c21ca-179">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c21ca-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c21ca-180">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c21ca-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="c21ca-181">Para reducir un archivo de datos o de registro</span><span class="sxs-lookup"><span data-stu-id="c21ca-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="c21ca-182">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c21ca-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c21ca-183">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c21ca-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c21ca-184">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c21ca-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c21ca-185">Este ejemplo usa [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) para reducir a 7 MB el tamaño de un archivo de datos denominado `DataFile1` de la base de datos `UserDB` .</span><span class="sxs-lookup"><span data-stu-id="c21ca-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="c21ca-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c21ca-186">See Also</span></span>  
 <span data-ttu-id="c21ca-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c21ca-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="c21ca-188">[Reducir una base de datos](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="c21ca-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="c21ca-189">[Eliminar archivos de datos o de registro de una base de datos](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="c21ca-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="c21ca-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c21ca-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="c21ca-191">sys.database_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c21ca-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
