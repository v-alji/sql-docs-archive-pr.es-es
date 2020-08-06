---
title: Reducir una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744123"
---
# <a name="shrink-a-database"></a><span data-ttu-id="3b405-102">Reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="3b405-102">Shrink a Database</span></span>
  <span data-ttu-id="3b405-103">En este tema se describe cómo reducir una base de datos mediante objetos de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b405-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3b405-104">La reducción de los archivos de datos permite recuperar espacio moviendo páginas de datos del final del archivo a espacio desocupado próximo al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="3b405-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="3b405-105">Cuando se crea suficiente espacio libre al final del archivo, las páginas de datos situadas al final del archivo pueden desasignarse y devolverse al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="3b405-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b405-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3b405-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3b405-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3b405-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3b405-108">El tamaño de la base de datos no puede ser menor que el tamaño mínimo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b405-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="3b405-109">El tamaño mínimo es el tamaño especificado cuando se creó la base de datos o el último tamaño establecido explícitamente mediante una operación de modificación del tamaño del archivo, como DBCC SHRINKFILE.</span><span class="sxs-lookup"><span data-stu-id="3b405-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="3b405-110">Por lo tanto, si se creó una base de datos con un tamaño de 10 MB y ha crecido hasta llegar a 100 MB, solo podrá reducirla hasta un tamaño de 10 MB, aunque se hayan eliminado todos los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b405-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="3b405-111">No se puede reducir una base de datos mientras se está realizando una copia de seguridad de la misma.</span><span class="sxs-lookup"><span data-stu-id="3b405-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="3b405-112">Asimismo, no se puede realizar una copia de seguridad de una base de datos mientras se está realizando una operación de reducción de ésta.</span><span class="sxs-lookup"><span data-stu-id="3b405-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="3b405-113">DBCC SHRINKDATABASE producirá un error cuando encuentra un índice de almacén de columnas optimizado de memoria xVelocity.</span><span class="sxs-lookup"><span data-stu-id="3b405-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="3b405-114">El trabajo realizado antes de encontrar el índice de almacén de columnas se llevará a cabo correctamente, por lo que es posible que la base de datos sea más pequeña.</span><span class="sxs-lookup"><span data-stu-id="3b405-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="3b405-115">Para completar DBCC SHRINKDATABASE, deshabilite todos los índices de almacén de columnas antes de ejecutar DBCC SHRINKDATABASE y, a continuación, vuelva a generar los índices de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="3b405-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3b405-116">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3b405-116">Recommendations</span></span>  
  
-   <span data-ttu-id="3b405-117">Para ver la cantidad actual de espacio disponible (sin asignar) en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b405-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="3b405-118">Para obtener más información, consulte [Mostrar la información del espacio ocupado por los datos y el registro de una base de datos](display-data-and-log-space-information-for-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="3b405-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="3b405-119">Tenga en cuenta la siguiente información cuando vaya a reducir una base de datos:</span><span class="sxs-lookup"><span data-stu-id="3b405-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="3b405-120">La reducción es más efectiva después de una operación que cree mucho espacio inutilizado, como por ejemplo una operación para truncar o eliminar tablas.</span><span class="sxs-lookup"><span data-stu-id="3b405-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="3b405-121">La mayoría de las bases de datos requieren que haya espacio disponible para realizar las operaciones diarias normales.</span><span class="sxs-lookup"><span data-stu-id="3b405-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="3b405-122">Si se reduce una base de datos en forma reiterada y su tamaño vuelve a aumentar, esto indica que el espacio que se redujo es necesario para las operaciones normales.</span><span class="sxs-lookup"><span data-stu-id="3b405-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="3b405-123">En estos casos, no sirve reducir la base de datos reiteradamente.</span><span class="sxs-lookup"><span data-stu-id="3b405-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="3b405-124">La reducción no mantiene el estado de fragmentación de los índices de la base de datos y generalmente aumenta la fragmentación hasta cierto punto.</span><span class="sxs-lookup"><span data-stu-id="3b405-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="3b405-125">Esta es otra razón para no reducir la base de datos reiteradamente.</span><span class="sxs-lookup"><span data-stu-id="3b405-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="3b405-126">A menos que tenga un requisito específico, no establezca la opción de base de datos AUTO_SHRINK en ON.</span><span class="sxs-lookup"><span data-stu-id="3b405-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3b405-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3b405-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3b405-128">Permisos</span><span class="sxs-lookup"><span data-stu-id="3b405-128">Permissions</span></span>  
 <span data-ttu-id="3b405-129">Debe pertenecer al rol fijo de servidor **sysadmin** o al rol fijo de base de datos **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="3b405-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3b405-130">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b405-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="3b405-131">Para reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="3b405-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="3b405-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="3b405-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3b405-133">Expanda **Bases de datos**y, después, haga clic con el botón derecho en la base de datos que quiera reducir.</span><span class="sxs-lookup"><span data-stu-id="3b405-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="3b405-134">Seleccione **Tareas**y **Reducir**, y haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="3b405-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="3b405-135">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="3b405-135">**Database**</span></span>  
     <span data-ttu-id="3b405-136">Muestra el nombre de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b405-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="3b405-137">**Espacio asignado actualmente**</span><span class="sxs-lookup"><span data-stu-id="3b405-137">**Current allocated space**</span></span>  
     <span data-ttu-id="3b405-138">Muestra el total de espacio utilizado y no utilizado de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b405-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="3b405-139">**Espacio disponible**</span><span class="sxs-lookup"><span data-stu-id="3b405-139">**Available free space**</span></span>  
     <span data-ttu-id="3b405-140">Muestra la suma del espacio disponible en los archivos de datos y de registro de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b405-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="3b405-141">**Reorganizar archivos antes de liberar espacio no utilizado**</span><span class="sxs-lookup"><span data-stu-id="3b405-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="3b405-142">Seleccionar esta opción equivale a ejecutar DBCC SHRINKDATABASE y especificar una opción de porcentaje de destino.</span><span class="sxs-lookup"><span data-stu-id="3b405-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="3b405-143">Desactivar esta opción equivale a ejecutar DBCC SHRINKDATABASE con la opción TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="3b405-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="3b405-144">De forma predeterminada, esta opción no está activada cuando se abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3b405-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="3b405-145">Si se selecciona se esta opción, el usuario debe especificar una opción de porcentaje de destino.</span><span class="sxs-lookup"><span data-stu-id="3b405-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="3b405-146">**Cantidad máxima de espacio disponible en los archivos tras la reducción**</span><span class="sxs-lookup"><span data-stu-id="3b405-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="3b405-147">Especifique el porcentaje máximo de espacio disponible que se va a dejar en los archivos de base de datos después de reducirla.</span><span class="sxs-lookup"><span data-stu-id="3b405-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="3b405-148">Los valores válidos están comprendidos entre 0 y 99.</span><span class="sxs-lookup"><span data-stu-id="3b405-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="3b405-149">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b405-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3b405-150">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b405-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="3b405-151">Para reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="3b405-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="3b405-152">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b405-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3b405-153">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3b405-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3b405-154">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3b405-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3b405-155">Este ejemplo usa [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) para reducir el tamaño de los archivos de datos y de registro de la base de datos `UserDB` , y para dejar un `10` por ciento de espacio disponible en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b405-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="3b405-156">Seguimiento: después de reducir una base de datos</span><span class="sxs-lookup"><span data-stu-id="3b405-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="3b405-157">Los datos que se mueven para reducir un archivo se pueden dispersar en cualquier ubicación disponible en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3b405-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="3b405-158">Esto produce la fragmentación de índices y puede reducir el rendimiento de las consultas que buscan un intervalo del índice.</span><span class="sxs-lookup"><span data-stu-id="3b405-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="3b405-159">Para eliminar la fragmentación, considere la posibilidad de volver a generar los índices en el archivo después de la reducción.</span><span class="sxs-lookup"><span data-stu-id="3b405-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b405-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b405-160">See Also</span></span>  
 <span data-ttu-id="3b405-161">[Reducir un archivo](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="3b405-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="3b405-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b405-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="3b405-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b405-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="3b405-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b405-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="3b405-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b405-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="3b405-166">Archivos y grupos de archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="3b405-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
