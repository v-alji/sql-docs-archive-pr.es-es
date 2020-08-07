---
title: Restaurar archivos y grupos de archivos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745829"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="9ddca-102">Restaurar archivos y grupos de archivos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ddca-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="9ddca-103">En este tema se describe cómo restaurar archivos y grupos de archivos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ddca-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9ddca-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9ddca-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9ddca-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9ddca-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ddca-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9ddca-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="9ddca-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ddca-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ddca-108">**Para restaurar archivos y grupos de archivos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9ddca-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="9ddca-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ddca-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9ddca-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ddca-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ddca-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9ddca-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9ddca-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9ddca-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9ddca-113">El administrador del sistema encargado de restaurar los archivos y grupos de archivos debe ser la única persona que esté utilizando la base de datos que se vaya a restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="9ddca-114">RESTORE no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="9ddca-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="9ddca-115">En el modelo de recuperación simple, el archivo debe pertenecer a un grupo de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9ddca-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="9ddca-116">En el modelo de recuperación completa o el modelo de recuperación optimizado para cargas masivas de registros, para poder restaurar archivos, debe realizar una copia de seguridad del registro de transacciones activo (conocido como el final del registro).</span><span class="sxs-lookup"><span data-stu-id="9ddca-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="9ddca-117">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="9ddca-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9ddca-118">Para restaurar una base de datos cifrada, debe tener acceso al certificado o la clave asimétrica que se usó para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="9ddca-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="9ddca-119">La base de datos no se puede restaurar sin el certificado o la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="9ddca-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="9ddca-120">Como resultado, se debe conservar el certificado que se usa para cifrar la clave de cifrado de base de datos mientras se necesite la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="9ddca-121">Para obtener más información, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="9ddca-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ddca-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ddca-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ddca-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="9ddca-123">Permissions</span></span>  
 <span data-ttu-id="9ddca-124">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9ddca-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="9ddca-125">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="9ddca-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="9ddca-126">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="9ddca-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="9ddca-127">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9ddca-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9ddca-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ddca-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="9ddca-129">Para restaurar archivos y grupos de archivos</span><span class="sxs-lookup"><span data-stu-id="9ddca-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="9ddca-130">Después de conectarse a la instancia adecuada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol.</span><span class="sxs-lookup"><span data-stu-id="9ddca-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9ddca-131">Expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-131">Expand **Databases**.</span></span> <span data-ttu-id="9ddca-132">En función de la base de datos, seleccione una base de datos de usuario o expanda **Bases de datos del sistema**y, a continuación, seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9ddca-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="9ddca-133">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, después, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="9ddca-134">Haga clic en **Archivos y grupos de archivos**para abrir el cuadro de diálogo **Restaurar archivos y grupos de archivos** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="9ddca-135">En la página **General** , en el cuadro de lista **A una base de datos** , especifique la base de datos que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="9ddca-136">Puede especificar una nueva base de datos o elegir una base de datos existente de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ddca-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="9ddca-137">La lista incluye todas las bases de datos del servidor, y excluye las bases de datos del sistema **master** y **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="9ddca-138">Para especificar el origen y la ubicación de los conjuntos de copias de seguridad que se deben restaurar, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ddca-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="9ddca-139">**Desde base de datos**</span><span class="sxs-lookup"><span data-stu-id="9ddca-139">**From database**</span></span>  
  
         <span data-ttu-id="9ddca-140">Escriba un nombre de base de datos en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="9ddca-140">Enter a database name in the list box.</span></span> <span data-ttu-id="9ddca-141">La lista contiene solo las bases de datos de las que se ha realizado una copia de seguridad, según el historial de copias de seguridad de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="9ddca-142">**Desde dispositivo**</span><span class="sxs-lookup"><span data-stu-id="9ddca-142">**From device**</span></span>  
  
         <span data-ttu-id="9ddca-143">Haga clic en el botón Examinar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-143">Click the browse button.</span></span> <span data-ttu-id="9ddca-144">En el cuadro de diálogo **Especificar dispositivos de copia de seguridad** , seleccione uno de los tipos de dispositivo enumerados en el cuadro de lista **Tipo de medio de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="9ddca-145">Para seleccionar uno o varios dispositivos del cuadro de lista **Medio para copia de seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="9ddca-146">Después de agregar los dispositivos que desee al cuadro de lista **Medio de copia de seguridad** , haga clic en **Aceptar** para volver a la página **General** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="9ddca-147">En la cuadrícula **Seleccionar los conjuntos de copia de seguridad que se van a restaurar** , seleccione las copias de seguridad que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="9ddca-148">En esta cuadrícula se muestran las copias de seguridad disponibles en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="9ddca-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="9ddca-149">De forma predeterminada, se sugiere un plan de recuperación.</span><span class="sxs-lookup"><span data-stu-id="9ddca-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="9ddca-150">Para anular el plan de recuperación sugerido, puede cambiar las selecciones de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9ddca-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="9ddca-151">Se anulará automáticamente la selección de aquellas copias de seguridad que dependan de una copia de seguridad cuya selección fue anulada.</span><span class="sxs-lookup"><span data-stu-id="9ddca-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="9ddca-152">Encabezado de columna</span><span class="sxs-lookup"><span data-stu-id="9ddca-152">Column head</span></span>|<span data-ttu-id="9ddca-153">Valores</span><span class="sxs-lookup"><span data-stu-id="9ddca-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="9ddca-154">**Restauración**</span><span class="sxs-lookup"><span data-stu-id="9ddca-154">**Restore**</span></span>|<span data-ttu-id="9ddca-155">Las casillas activadas indican los conjuntos de copias de seguridad que se restaurarán.</span><span class="sxs-lookup"><span data-stu-id="9ddca-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="9ddca-156">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9ddca-156">**Name**</span></span>|<span data-ttu-id="9ddca-157">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="9ddca-158">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="9ddca-158">**File Type**</span></span>|<span data-ttu-id="9ddca-159">Especifica el tipo de datos en la copia de seguridad: **Datos**, **Registro** o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="9ddca-160">Los datos contenidos en tablas están en archivos de **datos** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="9ddca-161">Los datos del registro de transacciones están en archivos de **registro** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="9ddca-162">Los datos de objetos binarios grandes (BLOB) que están almacenados en el sistema de archivos se encuentran en archivos de **datos de FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="9ddca-163">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9ddca-163">**Type**</span></span>|<span data-ttu-id="9ddca-164">Tipo de copia de seguridad realizada: **Completa**, **Diferencial** o **Registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="9ddca-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="9ddca-165">**Server**</span></span>|<span data-ttu-id="9ddca-166">Nombre de la instancia del motor de base de datos que ha realizado la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="9ddca-167">**Nombre lógico de archivo**</span><span class="sxs-lookup"><span data-stu-id="9ddca-167">**File Logical Name**</span></span>|<span data-ttu-id="9ddca-168">Nombre lógico del archivo.</span><span class="sxs-lookup"><span data-stu-id="9ddca-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="9ddca-169">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="9ddca-169">**Database**</span></span>|<span data-ttu-id="9ddca-170">Nombre de la base de datos para la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="9ddca-171">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="9ddca-171">**Start Date**</span></span>|<span data-ttu-id="9ddca-172">Fecha y hora en la que se inició la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ddca-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="9ddca-173">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="9ddca-173">**Finish Date**</span></span>|<span data-ttu-id="9ddca-174">Fecha y hora en la que finalizó la operación de copia de seguridad, presentadas en la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ddca-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="9ddca-175">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="9ddca-175">**Size**</span></span>|<span data-ttu-id="9ddca-176">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="9ddca-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="9ddca-177">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="9ddca-177">**User Name**</span></span>|<span data-ttu-id="9ddca-178">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="9ddca-179">Para ver o seleccionar las opciones avanzadas, haga clic en **Opciones** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="9ddca-180">En el panel **Opciones de restauración** , puede elegir cualquiera de las opciones siguientes si son apropiadas para su situación.</span><span class="sxs-lookup"><span data-stu-id="9ddca-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="9ddca-181">**Restaurar como grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="9ddca-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="9ddca-182">Indica que se está restaurando un grupo de archivos completo.</span><span class="sxs-lookup"><span data-stu-id="9ddca-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="9ddca-183">**Sobrescribir la base de datos existente**</span><span class="sxs-lookup"><span data-stu-id="9ddca-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="9ddca-184">Especifica que la operación de restauración debe sobrescribir las bases de datos especificadas y sus archivos relacionados, aunque ya exista otra base de datos u otro archivo con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9ddca-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="9ddca-185">La elección de esta opción equivale a utilizar la opción REPLACE en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="9ddca-186">**Preguntar antes de restaurar cada copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="9ddca-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="9ddca-187">Se le pedirá una confirmación antes de restaurar cada conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9ddca-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="9ddca-188">Esta opción es especialmente útil cuando hay que intercambiar cintas para distintos conjuntos de medios, como cuando el servidor dispone de un dispositivo de cinta.</span><span class="sxs-lookup"><span data-stu-id="9ddca-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="9ddca-189">**Restringir el acceso a la base de datos restaurada**</span><span class="sxs-lookup"><span data-stu-id="9ddca-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="9ddca-190">Hace que la base de datos restaurada esté disponible solo para los miembros de **db_owner**, **dbcreator**o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="9ddca-191">La selección de esta opción equivale al uso de la opción RESTRICTED_USER en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="9ddca-192">Si lo desea, puede restaurar la base de datos a una nueva ubicación si especifica un nuevo destino de restauración para cada archivo de la cuadrícula **Restaurar los archivos de base de datos como** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="9ddca-193">Encabezado de columna</span><span class="sxs-lookup"><span data-stu-id="9ddca-193">Column head</span></span>|<span data-ttu-id="9ddca-194">Valores</span><span class="sxs-lookup"><span data-stu-id="9ddca-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="9ddca-195">**Nombre del archivo original**</span><span class="sxs-lookup"><span data-stu-id="9ddca-195">**Original File Name**</span></span>|<span data-ttu-id="9ddca-196">La ruta de acceso completa de un archivo de copia de seguridad de origen.</span><span class="sxs-lookup"><span data-stu-id="9ddca-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="9ddca-197">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="9ddca-197">**File Type**</span></span>|<span data-ttu-id="9ddca-198">Especifica el tipo de datos en la copia de seguridad: **Datos**, **Registro** o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="9ddca-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="9ddca-199">Los datos contenidos en tablas están en archivos de **datos** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="9ddca-200">Los datos del registro de transacciones están en archivos de **registro** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="9ddca-201">Los datos de objetos binarios grandes (BLOB) que están almacenados en el sistema de archivos se encuentran en archivos de **datos de FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="9ddca-202">**Restaurar como**</span><span class="sxs-lookup"><span data-stu-id="9ddca-202">**Restore As**</span></span>|<span data-ttu-id="9ddca-203">La ruta de acceso completa del archivo de base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="9ddca-204">Para especificar un nuevo archivo de restauración, haga clic en el cuadro de texto y edite la ruta de acceso y el nombre de archivo que aparecen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ddca-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="9ddca-205">El hecho de cambiar la ruta de acceso o el nombre de archivo de la columna **Restaurar como** equivale a utilizar la opción MOVE en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="9ddca-206">El panel **Estado de recuperación** determina el estado de la base de datos después de la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="9ddca-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="9ddca-207">**Revertir las transacciones no confirmadas para dejar la base de datos lista para su uso. No pueden restaurarse registros de transacciones adicionales. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="9ddca-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="9ddca-208">Recupera la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ddca-208">Recovers the database.</span></span> <span data-ttu-id="9ddca-209">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9ddca-209">This is the default behavior.</span></span> <span data-ttu-id="9ddca-210">Elija esta opción únicamente si va a restaurar ahora todas las copias de seguridad necesarias.</span><span class="sxs-lookup"><span data-stu-id="9ddca-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="9ddca-211">Esta opción es equivalente a especificar WITH RECOVERY en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="9ddca-212">**Dejar la base de datos no operativa y no revertir las transacciones no confirmadas. Pueden restaurarse registros de transacciones adicionales. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="9ddca-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="9ddca-213">Deja la base de datos en estado de restauración.</span><span class="sxs-lookup"><span data-stu-id="9ddca-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="9ddca-214">Para recuperar la base de datos, debe realizar otra restauración con la opción RESTORE WITH RECOVERY anterior (vea el párrafo anterior).</span><span class="sxs-lookup"><span data-stu-id="9ddca-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="9ddca-215">Esta opción es equivalente a especificar WITH NORECOVERY en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="9ddca-216">Si selecciona esta opción, no estará disponible la opción **Conservar la configuración de replicación** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="9ddca-217">**Dejar la base de datos en modo de solo lectura. Revertir las transacciones sin confirmar, pero guardar las acciones de reversión en un archivo para que los efectos de recuperación puedan deshacerse (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="9ddca-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="9ddca-218">Deja la base de datos en estado de espera.</span><span class="sxs-lookup"><span data-stu-id="9ddca-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="9ddca-219">Esta opción es equivalente a especificar WITH STANDBY en una instrucción RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ddca-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="9ddca-220">Si elige esta opción, debe especificar un archivo en espera.</span><span class="sxs-lookup"><span data-stu-id="9ddca-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="9ddca-221">**Archivo para deshacer la reversión**</span><span class="sxs-lookup"><span data-stu-id="9ddca-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="9ddca-222">Especifique un nombre de archivo en espera en el cuadro de texto **Archivo para deshacer la reversión** .</span><span class="sxs-lookup"><span data-stu-id="9ddca-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="9ddca-223">Esta opción es necesaria si deja la base de datos en modo de solo lectura (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="9ddca-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9ddca-224">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ddca-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="9ddca-225">Para restaurar archivos y grupos de archivos</span><span class="sxs-lookup"><span data-stu-id="9ddca-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="9ddca-226">Ejecute la instrucción RESTORE DATABASE para restaurar la copia de seguridad de archivos y grupos de archivos; para ello, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ddca-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9ddca-227">El nombre de la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="9ddca-228">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ddca-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="9ddca-229">La cláusula FILE de cada archivo que desee restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="9ddca-230">La cláusula FILEGROUP de cada grupo de archivos que desee restaurar.</span><span class="sxs-lookup"><span data-stu-id="9ddca-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="9ddca-231">La cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9ddca-231">The NORECOVERY clause.</span></span> <span data-ttu-id="9ddca-232">Si los archivos no se han modificado desde que se creó la copia de seguridad, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9ddca-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="9ddca-233">Si los archivos se han modificado después de que se creara la copia de seguridad, ejecute la instrucción RESTORE LOG para aplicar la copia de seguridad del registro de transacciones y especifique:</span><span class="sxs-lookup"><span data-stu-id="9ddca-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="9ddca-234">El nombre de la base de datos a la que se aplicará el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9ddca-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="9ddca-235">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9ddca-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="9ddca-236">La cláusula NORECOVERY, si hay otra copia de seguridad del registro de transacciones que se deba aplicar después de la actual; de lo contrario, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="9ddca-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="9ddca-237">Las copias de seguridad del registro de transacciones, si se han aplicado, deben incluir el período de tiempo en el que se hizo la copia de seguridad de los archivos y grupos de archivos hasta el final del registro, a menos que se restauren TODOS los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ddca-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9ddca-238">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9ddca-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="9ddca-239">En este ejemplo se restauran los archivos y grupos de archivos de la base de datos `MyDatabase` .</span><span class="sxs-lookup"><span data-stu-id="9ddca-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="9ddca-240">Para restaurar la base de datos a la hora actual, se aplican dos registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9ddca-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ddca-241">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ddca-241">See Also</span></span>  
 <span data-ttu-id="9ddca-242">[Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9ddca-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="9ddca-243">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ddca-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="9ddca-244">[Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ddca-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="9ddca-245">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ddca-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="9ddca-246">[Restaurar una copia de seguridad del registro de transacciones &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ddca-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="9ddca-247">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ddca-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
