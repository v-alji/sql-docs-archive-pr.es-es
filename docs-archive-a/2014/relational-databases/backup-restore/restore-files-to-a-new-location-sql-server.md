---
title: Restaurar archivos en una nueva ubicación (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring databases [SQL Server], moving
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
ms.assetid: b4f4791d-646e-4632-9980-baae9cb1aade
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a8336e5d186fb72df4e0a17fdd9affccab4ee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745827"
---
# <a name="restore-files-to-a-new-location-sql-server"></a><span data-ttu-id="ce227-102">Restaurar archivos en una nueva ubicación (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ce227-102">Restore Files to a New Location (SQL Server)</span></span>
  <span data-ttu-id="ce227-103">En este tema se describe cómo restaurar archivos en una nueva ubicación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce227-103">This topic describes how to restore files to a new location in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ce227-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ce227-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ce227-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ce227-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ce227-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ce227-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ce227-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ce227-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ce227-108">**Para restaurar archivos en una nueva ubicación, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="ce227-108">**To restore files to a new location, using:**</span></span>  
  
     [<span data-ttu-id="ce227-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce227-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ce227-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce227-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ce227-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ce227-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ce227-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ce227-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ce227-113">El administrador del sistema encargado de restaurar los archivos debe ser la única persona que esté utilizando la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce227-113">The system administrator restoring the files must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="ce227-114">RESTORE no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="ce227-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="ce227-115">En el modelo de recuperación completa o el modelo de recuperación optimizado para cargas masivas de registros, para poder restaurar archivos, debe realizar una copia de seguridad del registro de transacciones activo (conocido como el final del registro).</span><span class="sxs-lookup"><span data-stu-id="ce227-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="ce227-116">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="ce227-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ce227-117">Para restaurar una base de datos cifrada, debe tener acceso al certificado o la clave asimétrica que se usó para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="ce227-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="ce227-118">La base de datos no se puede restaurar sin el certificado o la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="ce227-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="ce227-119">Como resultado, se debe conservar el certificado que se usa para cifrar la clave de cifrado de base de datos mientras se necesite la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce227-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="ce227-120">Para obtener más información, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ce227-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ce227-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ce227-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ce227-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="ce227-122">Permissions</span></span>  
 <span data-ttu-id="ce227-123">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="ce227-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="ce227-124">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="ce227-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="ce227-125">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="ce227-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="ce227-126">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="ce227-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ce227-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce227-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="ce227-128">Para restaurar archivos en una nueva ubicación</span><span class="sxs-lookup"><span data-stu-id="ce227-128">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="ce227-129">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expándala y, a continuación, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="ce227-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="ce227-130">Haga clic con el botón derecho en la base de datos que quiera, seleccione **Tareas**, **Restaurar**y, luego, haga clic en **Archivos y grupos de archivos**.</span><span class="sxs-lookup"><span data-stu-id="ce227-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="ce227-131">En la página **General** , en el cuadro de lista **A una base de datos** , especifique la base de datos que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="ce227-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="ce227-132">Puede especificar una nueva base de datos o elegir una base de datos existente de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ce227-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="ce227-133">La lista incluye todas las bases de datos del servidor, y excluye las bases de datos del sistema **master** y **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="ce227-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="ce227-134">Para especificar el origen y la ubicación de los conjuntos de copias de seguridad que se deben restaurar, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce227-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="ce227-135">**Desde base de datos**</span><span class="sxs-lookup"><span data-stu-id="ce227-135">**From database**</span></span>  
  
         <span data-ttu-id="ce227-136">Escriba un nombre de base de datos en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="ce227-136">Enter a database name in the list box.</span></span> <span data-ttu-id="ce227-137">La lista contiene solo las bases de datos de las que se ha realizado una copia de seguridad, según el historial de copias de seguridad de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ce227-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="ce227-138">**Desde dispositivo**</span><span class="sxs-lookup"><span data-stu-id="ce227-138">**From device**</span></span>  
  
         <span data-ttu-id="ce227-139">Haga clic en el botón Examinar.</span><span class="sxs-lookup"><span data-stu-id="ce227-139">Click the browse button.</span></span> <span data-ttu-id="ce227-140">En el cuadro de diálogo **Especificar dispositivos de copia de seguridad** , seleccione uno de los tipos de dispositivo enumerados en el cuadro de lista **Tipo de medio de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="ce227-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="ce227-141">Para seleccionar uno o varios dispositivos del cuadro de lista **Medio para copia de seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ce227-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="ce227-142">Después de agregar los dispositivos que desee al cuadro de lista **Medio de copia de seguridad** , haga clic en **Aceptar** para volver a la página **General** .</span><span class="sxs-lookup"><span data-stu-id="ce227-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="ce227-143">En la cuadrícula **Seleccionar los conjuntos de copia de seguridad que se van a restaurar** , seleccione las copias de seguridad que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="ce227-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="ce227-144">En esta cuadrícula se muestran las copias de seguridad disponibles en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="ce227-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="ce227-145">De forma predeterminada, se sugiere un plan de recuperación.</span><span class="sxs-lookup"><span data-stu-id="ce227-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="ce227-146">Para anular el plan de recuperación sugerido, puede cambiar las selecciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ce227-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="ce227-147">Se anulará automáticamente la selección de aquellas copias de seguridad que dependan de una copia de seguridad cuya selección fue anulada.</span><span class="sxs-lookup"><span data-stu-id="ce227-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="ce227-148">Encabezado de columna</span><span class="sxs-lookup"><span data-stu-id="ce227-148">Column head</span></span>|<span data-ttu-id="ce227-149">Valores</span><span class="sxs-lookup"><span data-stu-id="ce227-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="ce227-150">**Restauración**</span><span class="sxs-lookup"><span data-stu-id="ce227-150">**Restore**</span></span>|<span data-ttu-id="ce227-151">Las casillas activadas indican los conjuntos de copias de seguridad que se restaurarán.</span><span class="sxs-lookup"><span data-stu-id="ce227-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="ce227-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ce227-152">**Name**</span></span>|<span data-ttu-id="ce227-153">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce227-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="ce227-154">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="ce227-154">**File Type**</span></span>|<span data-ttu-id="ce227-155">Especifica el tipo de datos en la copia de seguridad: **Datos**, **Registro** o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="ce227-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="ce227-156">Los datos contenidos en tablas están en archivos de **datos** .</span><span class="sxs-lookup"><span data-stu-id="ce227-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="ce227-157">Los datos del registro de transacciones están en archivos de **registro** .</span><span class="sxs-lookup"><span data-stu-id="ce227-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="ce227-158">Los datos de objetos binarios grandes (BLOB) que están almacenados en el sistema de archivos se encuentran en archivos de **datos de FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="ce227-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="ce227-159">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce227-159">**Type**</span></span>|<span data-ttu-id="ce227-160">Tipo de copia de seguridad realizada: **Completa**, **Diferencial** o **Registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="ce227-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="ce227-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="ce227-161">**Server**</span></span>|<span data-ttu-id="ce227-162">Nombre de la instancia del motor de base de datos que ha realizado la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce227-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="ce227-163">**Nombre lógico de archivo**</span><span class="sxs-lookup"><span data-stu-id="ce227-163">**File Logical Name**</span></span>|<span data-ttu-id="ce227-164">Nombre lógico del archivo.</span><span class="sxs-lookup"><span data-stu-id="ce227-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="ce227-165">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="ce227-165">**Database**</span></span>|<span data-ttu-id="ce227-166">Nombre de la base de datos para la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce227-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="ce227-167">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="ce227-167">**Start Date**</span></span>|<span data-ttu-id="ce227-168">Fecha y hora en la que se inició la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="ce227-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="ce227-169">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="ce227-169">**Finish Date**</span></span>|<span data-ttu-id="ce227-170">Fecha y hora en la que finalizó la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="ce227-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="ce227-171">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="ce227-171">**Size**</span></span>|<span data-ttu-id="ce227-172">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ce227-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="ce227-173">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="ce227-173">**User Name**</span></span>|<span data-ttu-id="ce227-174">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce227-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="ce227-175">En el panel **Seleccionar una página** , haga clic en la página **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="ce227-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="ce227-176">En la cuadrícula **Restaurar archivos de base de datos como** , especifique una nueva ubicación para el archivo o archivos que desee mover.</span><span class="sxs-lookup"><span data-stu-id="ce227-176">In the **Restore database files as** grid, specify a new location for the file or files that you want to move.</span></span>  
  
    |<span data-ttu-id="ce227-177">Encabezado de columna</span><span class="sxs-lookup"><span data-stu-id="ce227-177">Column head</span></span>|<span data-ttu-id="ce227-178">Valores</span><span class="sxs-lookup"><span data-stu-id="ce227-178">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="ce227-179">**Nombre del archivo original**</span><span class="sxs-lookup"><span data-stu-id="ce227-179">**Original File Name**</span></span>|<span data-ttu-id="ce227-180">La ruta de acceso completa de un archivo de copia de seguridad de origen.</span><span class="sxs-lookup"><span data-stu-id="ce227-180">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="ce227-181">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="ce227-181">**File Type**</span></span>|<span data-ttu-id="ce227-182">Especifica el tipo de datos en la copia de seguridad: **Datos**, **Registro** o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="ce227-182">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="ce227-183">Los datos contenidos en tablas están en archivos de **datos** .</span><span class="sxs-lookup"><span data-stu-id="ce227-183">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="ce227-184">Los datos del registro de transacciones están en archivos de **registro** .</span><span class="sxs-lookup"><span data-stu-id="ce227-184">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="ce227-185">Los datos de objetos binarios grandes (BLOB) que están almacenados en el sistema de archivos se encuentran en archivos de **datos de FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="ce227-185">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="ce227-186">**Restaurar como**</span><span class="sxs-lookup"><span data-stu-id="ce227-186">**Restore As**</span></span>|<span data-ttu-id="ce227-187">La ruta de acceso completa del archivo de base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="ce227-187">The full path of the database file to be restored.</span></span> <span data-ttu-id="ce227-188">Para especificar un nuevo archivo de restauración, haga clic en el cuadro de texto y edite la ruta de acceso y el nombre de archivo que aparecen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce227-188">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="ce227-189">El hecho de cambiar la ruta de acceso o el nombre de archivo de la columna **Restaurar como** equivale a utilizar la opción MOVE en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce227-189">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ce227-190">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce227-190">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="ce227-191">Para restaurar archivos en una nueva ubicación</span><span class="sxs-lookup"><span data-stu-id="ce227-191">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="ce227-192">Si lo desea, ejecute la instrucción RESTORE FILELISTONLY para determinar el número de archivos y sus nombres en la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce227-192">Optionally, execute the RESTORE FILELISTONLY statement to determine the number and names of the files in the full database backup.</span></span>  
  
2.  <span data-ttu-id="ce227-193">Ejecute la instrucción RESTORE DATABASE para restaurar la copia de seguridad completa de la base de datos; para ello, especifique:</span><span class="sxs-lookup"><span data-stu-id="ce227-193">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="ce227-194">El nombre de la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="ce227-194">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="ce227-195">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce227-195">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="ce227-196">La cláusula MOVE para cada archivo que se vaya a restaurar en una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce227-196">The MOVE clause for each file to restore to a new location.</span></span>  
  
    -   <span data-ttu-id="ce227-197">La cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ce227-197">The NORECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="ce227-198">Si los archivos se han modificado después de que se creara la copia de seguridad, ejecute la instrucción RESTORE LOG para aplicar la copia de seguridad del registro de transacciones y especifique:</span><span class="sxs-lookup"><span data-stu-id="ce227-198">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="ce227-199">El nombre de la base de datos a la que se aplicará el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ce227-199">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="ce227-200">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ce227-200">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="ce227-201">La cláusula NORECOVERY, si hay otra copia de seguridad del registro de transacciones que se deba aplicar después de la actual; de lo contrario, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ce227-201">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="ce227-202">Las copias de seguridad del registro de transacciones, si se aplican, deben cubrir el período de tiempo en el que se hizo la copia de seguridad de los archivos y grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="ce227-202">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="ce227-203">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ce227-203">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ce227-204">En este ejemplo se restauran dos de los archivos de la base de datos `MyNwind` , que se encontraban originalmente en la unidad C, en ubicaciones nuevas de la unidad D. También se aplicarán dos registros de transacciones para restaurar la base de datos al momento actual.</span><span class="sxs-lookup"><span data-stu-id="ce227-204">This example restores two of the files for the `MyNwind` database that were originally located on Drive C to new locations on Drive D. Two transaction logs will also be applied to restore the database to the current time.</span></span> <span data-ttu-id="ce227-205">La instrucción `RESTORE FILELISTONLY` se usa para determinar el número y los nombres físicos y lógicos de los archivos de la base de datos que se están restaurando.</span><span class="sxs-lookup"><span data-stu-id="ce227-205">The `RESTORE FILELISTONLY` statement is used to determine the number and logical and physical names of the files in the database being restored.</span></span>  
  
```sql  
USE master;  
GO  
-- First determine the number and names of the files in the backup.  
RESTORE FILELISTONLY  
   FROM MyNwind_1;  
-- Restore the files for MyNwind.  
RESTORE DATABASE MyNwind  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   MOVE 'MyNwind_data_1' TO 'D:\MyData\MyNwind_data_1.mdf',   
   MOVE 'MyNwind_data_2' TO 'D:\MyData\MyNwind_data_2.ndf';  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce227-206">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce227-206">See Also</span></span>  
 <span data-ttu-id="ce227-207">[Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="ce227-207">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="ce227-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ce227-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="ce227-209">[Copiar bases de datos con Copias de seguridad y restauración](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="ce227-209">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="ce227-210">Restaurar archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ce227-210">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
  
