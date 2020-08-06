---
title: Restaurar archivos y grupos de archivos en archivos existentes (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
- overwriting filegroups
- overwriting files
ms.assetid: 517e07eb-9685-4b06-90af-b1cc496700b7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc72ae3ae2472fe579755fa624e9af6953c7aed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672118"
---
# <a name="restore-files-and-filegroups-over-existing-files-sql-server"></a><span data-ttu-id="9fe81-102">Restaurar archivos y grupos de archivos en archivos existentes (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9fe81-102">Restore Files and Filegroups over Existing Files (SQL Server)</span></span>
  <span data-ttu-id="9fe81-103">En este tema se describe cómo restaurar archivos y grupos de archivos sobre archivos existentes en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fe81-103">This topic describes how to restore files and filegroups over existing files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9fe81-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9fe81-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9fe81-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9fe81-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9fe81-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9fe81-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9fe81-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9fe81-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9fe81-108">**Para restaurar archivos y grupos de archivos sobre archivos existentes, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9fe81-108">**To restore files and filegroups over existing files, using:**</span></span>  
  
     [<span data-ttu-id="9fe81-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9fe81-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9fe81-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9fe81-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9fe81-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9fe81-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9fe81-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9fe81-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9fe81-113">El administrador del sistema encargado de restaurar los archivos y grupos de archivos debe ser la única persona que esté utilizando la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9fe81-113">The system administrator who is restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="9fe81-114">RESTORE no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="9fe81-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="9fe81-115">En el modelo de recuperación completa o el modelo de recuperación optimizado para cargas masivas de registros, para poder restaurar archivos, debe realizar una copia de seguridad del registro de transacciones activo (conocido como el final del registro).</span><span class="sxs-lookup"><span data-stu-id="9fe81-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="9fe81-116">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="9fe81-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9fe81-117">Para restaurar una base de datos cifrada, debe tener acceso al certificado o la clave asimétrica que se usó para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="9fe81-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="9fe81-118">La base de datos no se puede restaurar sin el certificado o la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="9fe81-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="9fe81-119">Como resultado, se debe conservar el certificado que se usa para cifrar la clave de cifrado de base de datos mientras se necesite la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fe81-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="9fe81-120">Para obtener más información, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="9fe81-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9fe81-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9fe81-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9fe81-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="9fe81-122">Permissions</span></span>  
 <span data-ttu-id="9fe81-123">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9fe81-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="9fe81-124">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="9fe81-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="9fe81-125">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="9fe81-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="9fe81-126">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9fe81-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9fe81-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9fe81-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="9fe81-128">Para restaurar archivos y grupos de archivos sobre archivos existentes</span><span class="sxs-lookup"><span data-stu-id="9fe81-128">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="9fe81-129">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expándala y, a continuación, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="9fe81-130">Haga clic con el botón derecho en la base de datos que quiera, seleccione **Tareas**, **Restaurar**y, luego, haga clic en **Archivos y grupos de archivos**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="9fe81-131">En la página **General** , en el cuadro de lista **A una base de datos** , especifique la base de datos que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="9fe81-132">Puede especificar una nueva base de datos o elegir una base de datos existente de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9fe81-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="9fe81-133">La lista incluye todas las bases de datos del servidor, y excluye las bases de datos del sistema **master** y **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="9fe81-134">Para especificar el origen y la ubicación de los conjuntos de copias de seguridad que se deben restaurar, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9fe81-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="9fe81-135">**Desde base de datos**</span><span class="sxs-lookup"><span data-stu-id="9fe81-135">**From database**</span></span>  
  
         <span data-ttu-id="9fe81-136">Escriba un nombre de base de datos en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="9fe81-136">Enter a database name in the list box.</span></span> <span data-ttu-id="9fe81-137">La lista contiene solo las bases de datos de las que se ha realizado una copia de seguridad, según el historial de copias de seguridad de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="9fe81-138">**Desde dispositivo**</span><span class="sxs-lookup"><span data-stu-id="9fe81-138">**From device**</span></span>  
  
         <span data-ttu-id="9fe81-139">Haga clic en el botón Examinar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-139">Click the browse button.</span></span> <span data-ttu-id="9fe81-140">En el cuadro de diálogo **Especificar dispositivos de copia de seguridad** , seleccione uno de los tipos de dispositivo enumerados en el cuadro de lista **Tipo de medio de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="9fe81-141">Para seleccionar uno o varios dispositivos del cuadro de lista **Medio para copia de seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="9fe81-142">Después de agregar los dispositivos que desee al cuadro de lista **Medio de copia de seguridad** , haga clic en **Aceptar** para volver a la página **General** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="9fe81-143">En la cuadrícula **Seleccionar los conjuntos de copia de seguridad que se van a restaurar** , seleccione las copias de seguridad que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="9fe81-144">En esta cuadrícula se muestran las copias de seguridad disponibles en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="9fe81-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="9fe81-145">De forma predeterminada, se sugiere un plan de recuperación.</span><span class="sxs-lookup"><span data-stu-id="9fe81-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="9fe81-146">Para anular el plan de recuperación sugerido, puede cambiar las selecciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9fe81-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="9fe81-147">Se anulará automáticamente la selección de aquellas copias de seguridad que dependan de una copia de seguridad cuya selección fue anulada.</span><span class="sxs-lookup"><span data-stu-id="9fe81-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="9fe81-148">Encabezado de columna</span><span class="sxs-lookup"><span data-stu-id="9fe81-148">Column head</span></span>|<span data-ttu-id="9fe81-149">Valores</span><span class="sxs-lookup"><span data-stu-id="9fe81-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="9fe81-150">**Restauración**</span><span class="sxs-lookup"><span data-stu-id="9fe81-150">**Restore**</span></span>|<span data-ttu-id="9fe81-151">Las casillas activadas indican los conjuntos de copias de seguridad que se restaurarán.</span><span class="sxs-lookup"><span data-stu-id="9fe81-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="9fe81-152">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9fe81-152">**Name**</span></span>|<span data-ttu-id="9fe81-153">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fe81-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="9fe81-154">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="9fe81-154">**File Type**</span></span>|<span data-ttu-id="9fe81-155">Especifica el tipo de datos en la copia de seguridad: **Datos**, **Registro** o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="9fe81-156">Los datos contenidos en tablas están en archivos de **datos** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="9fe81-157">Los datos del registro de transacciones están en archivos de **registro** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="9fe81-158">Los datos de objetos binarios grandes (BLOB) que están almacenados en el sistema de archivos se encuentran en archivos de **datos de FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="9fe81-159">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9fe81-159">**Type**</span></span>|<span data-ttu-id="9fe81-160">Tipo de copia de seguridad realizada: **Completa**, **Diferencial** o **Registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="9fe81-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="9fe81-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="9fe81-161">**Server**</span></span>|<span data-ttu-id="9fe81-162">Nombre de la instancia del motor de base de datos que ha realizado la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fe81-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="9fe81-163">**Nombre lógico de archivo**</span><span class="sxs-lookup"><span data-stu-id="9fe81-163">**File Logical Name**</span></span>|<span data-ttu-id="9fe81-164">Nombre lógico del archivo.</span><span class="sxs-lookup"><span data-stu-id="9fe81-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="9fe81-165">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="9fe81-165">**Database**</span></span>|<span data-ttu-id="9fe81-166">Nombre de la base de datos para la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fe81-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="9fe81-167">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="9fe81-167">**Start Date**</span></span>|<span data-ttu-id="9fe81-168">Fecha y hora en la que se inició la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="9fe81-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="9fe81-169">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="9fe81-169">**Finish Date**</span></span>|<span data-ttu-id="9fe81-170">Fecha y hora en la que finalizó la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="9fe81-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="9fe81-171">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="9fe81-171">**Size**</span></span>|<span data-ttu-id="9fe81-172">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="9fe81-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="9fe81-173">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="9fe81-173">**User Name**</span></span>|<span data-ttu-id="9fe81-174">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fe81-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="9fe81-175">En el panel **Seleccionar una página** , haga clic en la página **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="9fe81-176">En el panel **Opciones de restauración** , seleccione **Sobrescribir la base de datos existente (WITH REPLACE)** .</span><span class="sxs-lookup"><span data-stu-id="9fe81-176">In the **Restore options** panel, select **Overwrite the existing database (WITH REPLACE)**.</span></span> <span data-ttu-id="9fe81-177">La operación de restauración sobrescribe las bases de datos especificadas y sus archivos relacionados, aunque ya exista otra base de datos u otro archivo con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9fe81-177">The restore operation overwrites any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9fe81-178">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9fe81-178">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="9fe81-179">Para restaurar archivos y grupos de archivos sobre archivos existentes</span><span class="sxs-lookup"><span data-stu-id="9fe81-179">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="9fe81-180">Ejecute la instrucción RESTORE DATABASE para restaurar la copia de seguridad de archivos y grupos de archivos; para ello, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fe81-180">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9fe81-181">El nombre de la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-181">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="9fe81-182">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9fe81-182">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="9fe81-183">La cláusula FILE de cada archivo que desee restaurar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-183">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="9fe81-184">La cláusula FILEGROUP de cada grupo de archivos que desee restaurar.</span><span class="sxs-lookup"><span data-stu-id="9fe81-184">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="9fe81-185">La opción REPLACE para especificar que cada archivo se puede restaurar sobre archivos existentes que tengan el mismo nombre y ubicación.</span><span class="sxs-lookup"><span data-stu-id="9fe81-185">The REPLACE option to specify that each file can be restored over existing files of the same name and location.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="9fe81-186">Utilice la opción REPLACE con precaución.</span><span class="sxs-lookup"><span data-stu-id="9fe81-186">Use the REPLACE option cautiously.</span></span> <span data-ttu-id="9fe81-187">Para obtener más información, consulte el elemento .</span><span class="sxs-lookup"><span data-stu-id="9fe81-187">For more information, see .</span></span>  
  
    -   <span data-ttu-id="9fe81-188">Opción NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9fe81-188">The NORECOVERY option.</span></span> <span data-ttu-id="9fe81-189">Si los archivos no se han modificado desde que se creó la copia de seguridad, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9fe81-189">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="9fe81-190">Si los archivos se han modificado después de que se creara la copia de seguridad, ejecute la instrucción RESTORE LOG para aplicar la copia de seguridad del registro de transacciones y especifique:</span><span class="sxs-lookup"><span data-stu-id="9fe81-190">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9fe81-191">El nombre de la base de datos a la que se aplicará el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9fe81-191">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="9fe81-192">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9fe81-192">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="9fe81-193">La cláusula NORECOVERY, si hay otra copia de seguridad del registro de transacciones que se deba aplicar después de la actual; de lo contrario, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9fe81-193">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="9fe81-194">Las copias de seguridad del registro de transacciones, si se aplican, deben cubrir el período de tiempo en el que se hizo la copia de seguridad de los archivos y grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="9fe81-194">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9fe81-195">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9fe81-195">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="9fe81-196">En el siguiente ejemplo se restauran los archivos y grupos de archivos de la base de datos `MyNwind` y se reemplaza cualquier archivo existente del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9fe81-196">The following example restores the files and filegroups for the `MyNwind` database, and replaces any existing files of the same name.</span></span> <span data-ttu-id="9fe81-197">También se aplicarán dos registros de transacciones para restaurar la base de datos a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="9fe81-197">Two transaction logs will also be applied to restore the database to the current time.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyNwind.  
RESTORE DATABASE MyNwind  
   FILE = 'MyNwind_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyNwind_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   REPLACE;  
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
  
## <a name="see-also"></a><span data-ttu-id="9fe81-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fe81-198">See Also</span></span>  
 <span data-ttu-id="9fe81-199">[Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9fe81-199">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="9fe81-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9fe81-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="9fe81-201">[Restaurar archivos y grupos de archivos &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9fe81-201">[Restore Files and Filegroups &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="9fe81-202">Copiar bases de datos con Copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="9fe81-202">Copy Databases with Backup and Restore</span></span>](../databases/copy-databases-with-backup-and-restore.md)  
  
  
