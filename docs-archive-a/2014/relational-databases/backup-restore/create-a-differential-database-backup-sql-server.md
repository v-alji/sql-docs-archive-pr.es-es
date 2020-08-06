---
title: Creación de una copia de seguridad diferencial de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677705"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="b5f14-102">Crear una copia de seguridad diferencial de una base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b5f14-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="b5f14-103">En este tema se describe cómo crear una copia de seguridad de una base de datos diferencial en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5f14-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b5f14-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b5f14-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5f14-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b5f14-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5f14-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b5f14-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b5f14-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5f14-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b5f14-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b5f14-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b5f14-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b5f14-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5f14-110">**Para crear una copia de seguridad de una base de datos diferencial, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="b5f14-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="b5f14-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5f14-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5f14-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5f14-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5f14-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b5f14-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b5f14-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b5f14-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b5f14-115">La instrucción BACKUP no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="b5f14-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b5f14-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5f14-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="b5f14-117">La creación de una copia de seguridad diferencial de base de datos requiere que haya una copia de seguridad de base de datos completa previa.</span><span class="sxs-lookup"><span data-stu-id="b5f14-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="b5f14-118">Si nunca se ha hecho una copia de seguridad de la base de datos seleccionada, realice una copia de seguridad de base de datos completa antes de crear la copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="b5f14-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="b5f14-119">Para obtener más información, vea [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b5f14-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b5f14-120">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b5f14-120">Recommendations</span></span>  
  
-   <span data-ttu-id="b5f14-121">A medida que se incrementa el tamaño de las copias de seguridad diferenciales, la restauración de una copia de seguridad diferencial puede incrementar sensiblemente el tiempo necesario para restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f14-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="b5f14-122">Por ello, recomendamos que realice una copia de seguridad completa a intervalos definidos para establecer una nueva base diferencial para los datos.</span><span class="sxs-lookup"><span data-stu-id="b5f14-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="b5f14-123">Por ejemplo, cada semana podría realizar una copia de seguridad completa de toda la base de datos (es decir, una copia de seguridad completa de la base de datos) seguida de una serie de copias de seguridad diferenciales de la base de datos realizadas periódicamente durante la semana.</span><span class="sxs-lookup"><span data-stu-id="b5f14-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5f14-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b5f14-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5f14-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="b5f14-125">Permissions</span></span>  
 <span data-ttu-id="b5f14-126">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="b5f14-127">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5f14-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b5f14-128">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="b5f14-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="b5f14-129">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="b5f14-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="b5f14-130">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="b5f14-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5f14-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5f14-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="b5f14-132">Para crear una copia de seguridad diferencial de una base de datos</span><span class="sxs-lookup"><span data-stu-id="b5f14-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="b5f14-133">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b5f14-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b5f14-134">Expanda **Bases de datos**y, dependiendo de la base de datos, seleccione una base de datos de usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="b5f14-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b5f14-135">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b5f14-136">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b5f14-137">En el cuadro de lista **Base de datos** , compruebe el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f14-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="b5f14-138">También puede seleccionar otra base de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="b5f14-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="b5f14-139">Puede realizar una copia de seguridad diferencial para cualquier modelo de recuperación (completa, registro masivo o simple).</span><span class="sxs-lookup"><span data-stu-id="b5f14-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="b5f14-140">En el cuadro de lista **Tipo de copia de seguridad** , seleccione **Diferencial**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b5f14-141">Una vez seleccionado **Diferencial**, compruebe que esté desactivada la casilla **Copia de seguridad de solo copia**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="b5f14-142">En **Componente de copia de seguridad**, haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="b5f14-143">Acepte el nombre del conjunto de copia de seguridad predeterminado sugerido en el cuadro de texto **Nombre** o especifique otro nombre.</span><span class="sxs-lookup"><span data-stu-id="b5f14-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="b5f14-144">Opcionalmente, en el cuadro de texto **Descripción** , escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5f14-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="b5f14-145">Especifique cuándo expirará el conjunto de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="b5f14-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="b5f14-146">Para que el conjunto de copia de seguridad expire al cabo de un número de días específico, haga clic en **Después de** (opción predeterminada) y escriba el número de días tras la creación del conjunto en que este expirará.</span><span class="sxs-lookup"><span data-stu-id="b5f14-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="b5f14-147">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="b5f14-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="b5f14-148">El valor predeterminado se establece en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** del cuadro de diálogo **Propiedades del servidor** (página**Configuración de base de datos** ).</span><span class="sxs-lookup"><span data-stu-id="b5f14-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="b5f14-149">Para acceder a esta opción, en el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y seleccione Propiedades; después, seleccione la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="b5f14-150">Para que el conjunto de copia de seguridad expire en una determinada fecha, haga clic en **El**y escriba la fecha en la que expirará.</span><span class="sxs-lookup"><span data-stu-id="b5f14-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="b5f14-151">Elija el tipo de destino de la copia de seguridad haciendo clic en **Disco** o **Cinta**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="b5f14-152">Para seleccionar la ruta de acceso de hasta 64 unidades de disco o cinta que contengan un solo conjunto de medios, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="b5f14-153">Las rutas seleccionadas se muestran en el cuadro de lista **Copia de seguridad en** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="b5f14-154">Para eliminar un destino de copia de seguridad, selecciónelo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="b5f14-155">Para ver el contenido de un destino de copia de seguridad, selecciónelo y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="b5f14-156">Para ver o seleccionar las opciones avanzadas, haga clic en **Opciones** , en el panel **Seleccionar una página** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="b5f14-157">Seleccione una opción de **Sobrescribir medios** ; para ello, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5f14-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="b5f14-158">**Hacer copia de seguridad en el conjunto de medios existente**</span><span class="sxs-lookup"><span data-stu-id="b5f14-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="b5f14-159">Para esta opción, haga clic en **Anexar al conjunto de copia de seguridad existente** o **Sobrescribir todos los conjuntos de copia de seguridad existentes**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="b5f14-160">Opcionalmente, seleccione la casilla **Comprobar nombre de conjunto de medios y fecha de expiración de conjunto de copia** y, si lo desea, especifique un nombre en el cuadro de texto **Nombre del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="b5f14-161">Si no especifica ningún nombre, se creará un conjunto de medios con un nombre en blanco.</span><span class="sxs-lookup"><span data-stu-id="b5f14-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="b5f14-162">Si especifica un nombre para el conjunto, los medios (cinta o disco) se comprueban para ver si el nombre real coincide con el nombre especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="b5f14-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="b5f14-163">Si deja el nombre del conjunto de medios en blanco y selecciona la casilla para comprobarlo con los medios, el resultado correcto significará que el nombre del conjunto en los medios también está en blanco.</span><span class="sxs-lookup"><span data-stu-id="b5f14-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="b5f14-164">**Hacer copia de seguridad en un nuevo conjunto de medios y borrar todos los conjuntos de copia de seguridad existentes**</span><span class="sxs-lookup"><span data-stu-id="b5f14-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="b5f14-165">Para esta opción, especifique un nombre en el cuadro de texto **Nuevo nombre del conjunto de medios** y, si lo desea, describa el conjunto de medios en el cuadro de texto **Nueva descripción del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="b5f14-166">Opcionalmente, en la sección **Confiabilidad** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="b5f14-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="b5f14-167">**Comprobar copia de seguridad al finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="b5f14-168">**Realizar suma de comprobación antes de escribir en los medios**y, si lo desea, **Continuar después de un error de suma de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="b5f14-169">Para obtener más información sobre las sumas de comprobación, vea [Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b5f14-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="b5f14-170">Si va a realizar copias de seguridad en una unidad de cinta (según se haya especificado en la sección **Destino** de la página **General** ), la opción **Descargar la cinta después de realizar la copia de seguridad** está activa.</span><span class="sxs-lookup"><span data-stu-id="b5f14-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="b5f14-171">Al hacer clic en esta opción se activa la opción **Rebobinar la cinta antes de descargar** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5f14-172">Las opciones de la sección **Registro de transacciones** se encuentran inactivas salvo que vaya a realizar una copia de seguridad de un registro de transacciones (según se haya especificado en la sección **Tipo de copia de seguridad** de la página **General** ).</span><span class="sxs-lookup"><span data-stu-id="b5f14-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="b5f14-173">y las versiones posteriores admiten la [compresión de copia de seguridad](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b5f14-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="b5f14-174">De forma predeterminada, el hecho de que se comprima una copia de seguridad depende del valor de la opción de configuración del servidor **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="b5f14-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="b5f14-175">Pero, independientemente del valor predeterminado actual de nivel de servidor, puede comprimir una copia de seguridad si activa **Comprimir copia de seguridad**e impedir la compresión si activa **No comprimir copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="b5f14-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="b5f14-176">**Para ver el valor predeterminado actual de la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="b5f14-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="b5f14-177">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="b5f14-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5f14-178">Como alternativa para crear copias de seguridad diferenciales de bases de datos, puede utilizar el Asistente para planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b5f14-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5f14-179">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5f14-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="b5f14-180">Para crear una copia de seguridad diferencial de una base de datos</span><span class="sxs-lookup"><span data-stu-id="b5f14-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="b5f14-181">Ejecute la instrucción BACKUP DATABASE para crear la copia de seguridad de base de datos diferencial, especificando:</span><span class="sxs-lookup"><span data-stu-id="b5f14-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="b5f14-182">El nombre de la base de datos de la que se va a realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5f14-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="b5f14-183">El dispositivo de copia de seguridad en el que se escribe la copia de seguridad de base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="b5f14-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="b5f14-184">La cláusula DIFFERENTIAL, para especificar que solo se realice una copia de seguridad de las partes de la base de datos que han cambiado desde la última copia de seguridad de base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="b5f14-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="b5f14-185">La sintaxis necesaria es:</span><span class="sxs-lookup"><span data-stu-id="b5f14-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="b5f14-186">BACKUP DATABASE *nombre_base_de_datos* TO <dispositivo_copia_seguridad> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="b5f14-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b5f14-187">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b5f14-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="b5f14-188">En este ejemplo se crea una copia de seguridad de una base de datos diferencial y una base de datos completa para la base de datos `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="b5f14-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5f14-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5f14-189">See Also</span></span>  
 <span data-ttu-id="b5f14-190">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b5f14-191">[Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="b5f14-192">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="b5f14-193">[Restaurar una copia de seguridad diferencial de la base de datos &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="b5f14-194">[Restaurar una copia de seguridad del registro de transacciones &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="b5f14-195">[Planes de mantenimiento](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="b5f14-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="b5f14-196">Copias de seguridad de archivos completas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5f14-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
