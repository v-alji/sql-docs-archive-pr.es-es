---
title: Realizar copias de seguridad de un registro de transacciones (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672138"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="9d408-102">Realizar copia de seguridad de un registro de transacciones (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d408-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="9d408-103">En este tema se describe cómo realizar una copia de seguridad de un registro de transacciones en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d408-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="9d408-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9d408-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9d408-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9d408-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9d408-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9d408-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9d408-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="9d408-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9d408-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9d408-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9d408-109">**Para realizar una copia de seguridad de un registro de transacciones, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9d408-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="9d408-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9d408-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9d408-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9d408-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9d408-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d408-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d408-113"> Como alternativa, puede utilizar el[Asistente para planes de mantenimiento](../maintenance-plans/use-the-maintenance-plan-wizard.md)para crear copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9d408-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="9d408-114">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9d408-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9d408-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9d408-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9d408-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9d408-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9d408-117">La instrucción BACKUP no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="9d408-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9d408-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="9d408-118">Recommendations</span></span>  
  
-   <span data-ttu-id="9d408-119">Si una base de datos utiliza el modelo de recuperación optimizado para cargas masivas de registros o completo, debe hacer una copia de seguridad del registro de transacciones con suficiente regularidad como para proteger los datos e impedir que el registro de transacciones se llene.</span><span class="sxs-lookup"><span data-stu-id="9d408-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="9d408-120">De este modo se trunca el registro y se admite la restauración de la base de datos a un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="9d408-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="9d408-121">De forma predeterminada, cada operación de copia de seguridad correcta agrega una entrada en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y en el registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9d408-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="9d408-122">Si hace una copia de seguridad del registro de transacciones con frecuencia, estos mensajes que indican la corrección de la operación pueden acumularse rápidamente, con lo que se crean registros de errores muy grandes que pueden dificultar la búsqueda de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="9d408-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="9d408-123">En esos casos, puede suprimir estas entradas de registro utilizando la marca de seguimiento 3226 si ninguno de los scripts depende de esas entradas.</span><span class="sxs-lookup"><span data-stu-id="9d408-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="9d408-124">Para obtener más información, vea [Marcas de seguimiento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9d408-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9d408-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9d408-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9d408-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="9d408-126">Permissions</span></span>  
 <span data-ttu-id="9d408-127">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="9d408-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="9d408-128">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9d408-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9d408-129">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="9d408-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="9d408-130">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="9d408-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="9d408-131">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="9d408-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9d408-132">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9d408-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="9d408-133">Para realizar una copia de seguridad de un registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="9d408-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="9d408-134">Después de conectarse a la instancia apropiada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="9d408-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9d408-135">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9d408-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9d408-136">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="9d408-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="9d408-137">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="9d408-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="9d408-138">En el cuadro de lista **Base de datos** , compruebe el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9d408-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="9d408-139">También puede seleccionar otra base de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="9d408-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="9d408-140">Compruebe que el modelo de recuperación sea **FULL** o **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="9d408-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="9d408-141">En el cuadro de lista **Tipo de copia de seguridad** , seleccione **Registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="9d408-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="9d408-142">También puede seleccionar **Copia de seguridad de solo copia** para crear un copia de seguridad de solo copia.</span><span class="sxs-lookup"><span data-stu-id="9d408-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="9d408-143">Una *copia de seguridad de solo copia* es una copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente de la secuencia de copias de seguridad convencionales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d408-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="9d408-144">Para obtener más información, vea [Copias de seguridad de solo copia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9d408-145">Cuando la opción **Diferencial** está seleccionada, no puede crear una copia de seguridad de solo copia.</span><span class="sxs-lookup"><span data-stu-id="9d408-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="9d408-146">Acepte el nombre del conjunto de copia de seguridad predeterminado sugerido en el cuadro de texto **Nombre** o especifique otro nombre.</span><span class="sxs-lookup"><span data-stu-id="9d408-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="9d408-147">Opcionalmente, en el cuadro de texto **Descripción** , escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9d408-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="9d408-148">Especifique cuándo expirará el conjunto de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="9d408-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="9d408-149">Para que el conjunto de copia de seguridad expire al cabo de un número de días específico, haga clic en **Después de** (opción predeterminada) y escriba el número de días tras la creación del conjunto en que este expirará.</span><span class="sxs-lookup"><span data-stu-id="9d408-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="9d408-150">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="9d408-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="9d408-151">El valor predeterminado se establece en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** del cuadro de diálogo **Propiedades del servidor** (página**Configuración de base de datos** ).</span><span class="sxs-lookup"><span data-stu-id="9d408-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="9d408-152">Para tener acceso a este cuadro de diálogo, haga clic con el botón derecho en el nombre del servidor en el Explorador de objetos y seleccione Propiedades. Después, seleccione la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="9d408-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="9d408-153">Para que el conjunto de copia de seguridad expire en una determinada fecha, haga clic en **El**y escriba la fecha en la que expirará.</span><span class="sxs-lookup"><span data-stu-id="9d408-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="9d408-154">Elija el tipo de destino de la copia de seguridad haciendo clic en **Disco**, **Dirección URL** o **Cinta**.</span><span class="sxs-lookup"><span data-stu-id="9d408-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="9d408-155">Para seleccionar las rutas de acceso de hasta 64 unidades de disco o cinta que contienen un solo conjunto de medios, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9d408-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="9d408-156">Las rutas seleccionadas se muestran en el cuadro de lista **Copia de seguridad en** .</span><span class="sxs-lookup"><span data-stu-id="9d408-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="9d408-157">Para eliminar un destino de copia de seguridad, selecciónelo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="9d408-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="9d408-158">Para ver el contenido de un destino de copia de seguridad, selecciónelo y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="9d408-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="9d408-159">Para ver o seleccionar las opciones avanzadas, haga clic en **Opciones** , en el panel **Seleccionar una página** .</span><span class="sxs-lookup"><span data-stu-id="9d408-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="9d408-160">Seleccione una opción de **Sobrescribir medios** ; para ello, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d408-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="9d408-161">**Hacer copia de seguridad en el conjunto de medios existente**</span><span class="sxs-lookup"><span data-stu-id="9d408-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="9d408-162">Para esta opción, haga clic en **Anexar al conjunto de copia de seguridad existente** o **Sobrescribir todos los conjuntos de copia de seguridad existentes**.</span><span class="sxs-lookup"><span data-stu-id="9d408-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="9d408-163">Para obtener más información, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="9d408-164">Opcionalmente, seleccione **Comprobar nombre de conjunto de medios y fecha de expiración del conjunto de copia de seguridad** para que la operación de copia de seguridad compruebe la fecha y la hora en que expiran el conjunto de medios y el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9d408-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="9d408-165">También puede escribir un nombre en el cuadro de texto **Nombre del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="9d408-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="9d408-166">Si no especifica ningún nombre, se creará un conjunto de medios con un nombre en blanco.</span><span class="sxs-lookup"><span data-stu-id="9d408-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="9d408-167">Si especifica un nombre para el conjunto, los medios (cinta o disco) se comprueban para ver si el nombre real coincide con el nombre especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="9d408-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="9d408-168">Si deja el nombre del conjunto de medios en blanco y selecciona la casilla para comprobarlo con los medios, el resultado correcto significará que el nombre del conjunto en los medios también está en blanco.</span><span class="sxs-lookup"><span data-stu-id="9d408-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="9d408-169">**Hacer copia de seguridad en un nuevo conjunto de medios y borrar todos los conjuntos de copia de seguridad existentes**</span><span class="sxs-lookup"><span data-stu-id="9d408-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="9d408-170">Para esta opción, especifique un nombre en el cuadro de texto **Nuevo nombre del conjunto de medios** y, si lo desea, describa el conjunto de medios en el cuadro de texto **Nueva descripción del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="9d408-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="9d408-171">Para obtener más información, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="9d408-172">Opcionalmente, en la sección **Confiabilidad** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="9d408-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="9d408-173">**Comprobar copia de seguridad al finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9d408-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="9d408-174">**Realizar suma de comprobación antes de escribir en los medios**y, si lo desea, **Continuar después de un error de suma de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="9d408-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="9d408-175">Para obtener más información sobre las sumas de comprobación, vea [Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="9d408-176">En la sección **Registro de transacciones** :</span><span class="sxs-lookup"><span data-stu-id="9d408-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="9d408-177">Para las copias de seguridad rutinarias del registro, conserve la selección predeterminada **Truncar el registro de transacciones quitando las entradas inactivas**.</span><span class="sxs-lookup"><span data-stu-id="9d408-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="9d408-178">Para hacer una copia de seguridad del final del registro (es decir, del registro activo), active **Realizar copia de seguridad del final del registro y dejar la base de datos en estado de restauración**.</span><span class="sxs-lookup"><span data-stu-id="9d408-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="9d408-179">Una copia del final del registro se lleva a cabo cuando no se consigue realizar la copia de seguridad del final de registro para impedir la pérdida de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9d408-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="9d408-180">Realice una copia de seguridad del registro activo (copia del final del registro) después de un error, antes de comenzar la restauración de la base de datos o cuando se conmuta por error a una base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="9d408-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="9d408-181">Esta opción equivale a especificar la opción NORECOVERY en la instrucción BACKUP LOG de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="9d408-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="9d408-182">Para obtener más información sobre las copias del final del registro, vea [Copias del final del registro &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="9d408-183">Si va a realizar copias de seguridad en una unidad de cinta (según se haya especificado en la sección **Destino** de la página **General** ), la opción **Descargar la cinta después de realizar la copia de seguridad** está activa.</span><span class="sxs-lookup"><span data-stu-id="9d408-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="9d408-184">Al hacer clic en esta opción se activa la opción **Rebobinar la cinta antes de descargar** .</span><span class="sxs-lookup"><span data-stu-id="9d408-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="9d408-185">y las versiones posteriores admiten la [compresión de copia de seguridad](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="9d408-186">De forma predeterminada, el hecho de que se comprima una copia de seguridad depende del valor de la opción de configuración del servidor **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="9d408-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="9d408-187">Pero, independientemente del valor predeterminado actual de nivel de servidor, puede comprimir una copia de seguridad si activa **Comprimir copia de seguridad**e impedir la compresión si activa **No comprimir copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="9d408-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="9d408-188">**Para ver el valor predeterminado actual de la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="9d408-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="9d408-189">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="9d408-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="9d408-190">**Cifrado**</span><span class="sxs-lookup"><span data-stu-id="9d408-190">**Encryption**</span></span>  
  
 <span data-ttu-id="9d408-191">Para cifrar el archivo de copia de seguridad, active la casilla **Cifrar copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9d408-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="9d408-192">Seleccione un algoritmo de cifrado que utilizar para cifrar el archivo de copia de seguridad y proporcione un certificado o clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="9d408-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="9d408-193">Los algoritmos disponibles para el cifrado son:</span><span class="sxs-lookup"><span data-stu-id="9d408-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="9d408-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="9d408-194">AES 128</span></span>  
  
-   <span data-ttu-id="9d408-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="9d408-195">AES 192</span></span>  
  
-   <span data-ttu-id="9d408-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="9d408-196">AES 256</span></span>  
  
-   <span data-ttu-id="9d408-197">Triple DES</span><span class="sxs-lookup"><span data-stu-id="9d408-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9d408-198">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9d408-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="9d408-199">Para realizar una copia de seguridad de un registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="9d408-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="9d408-200">Ejecute la instrucción BACKUP LOG para realizar una copia de seguridad del registro de transacciones y especifique:</span><span class="sxs-lookup"><span data-stu-id="9d408-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="9d408-201">El nombre de la base de datos a la que pertenece el registro de transacciones del que se desea hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9d408-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="9d408-202">El dispositivo de copia de seguridad en el que se va a escribir la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9d408-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9d408-203">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d408-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9d408-204">En este ejemplo se utiliza la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , que utiliza el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="9d408-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="9d408-205">Con el fin de permitir copias de seguridad de registros, antes de realizar una copia de seguridad completa de la base de datos, la base de datos se ha configurado para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="9d408-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="9d408-206">Para obtener más información, vea [Ver o cambiar el modelo de recuperación de una base de datos &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="9d408-207">En este ejemplo se crea una copia de seguridad del registro de transacciones de la base de datos [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] en el dispositivo de copia de seguridad creado anteriormente, `MyAdvWorks_FullRM_log1`.</span><span class="sxs-lookup"><span data-stu-id="9d408-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9d408-208">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d408-208">Using PowerShell</span></span>  
  
<span data-ttu-id="9d408-209">Utilice el cmdlet `Backup-SqlDatabase` y especifique `Log` como el valor del parámetro `-BackupAction`.</span><span class="sxs-lookup"><span data-stu-id="9d408-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="9d408-210">En el ejemplo siguiente se crea una copia de seguridad de registro de la base de datos `MyDB` en la ubicación de copia de seguridad predeterminada de la instancia de servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="9d408-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="9d408-211">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9d408-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9d408-212">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9d408-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9d408-213">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9d408-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="9d408-214">Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9d408-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="9d408-215">Solucionar problemas de un registro de transacciones lleno &#40;Error 9002 de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9d408-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d408-216">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d408-216">See Also</span></span>  
 <span data-ttu-id="9d408-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d408-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9d408-218">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9d408-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="9d408-219">[Planes de mantenimiento](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="9d408-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="9d408-220">Copias de seguridad de archivos completas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9d408-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
