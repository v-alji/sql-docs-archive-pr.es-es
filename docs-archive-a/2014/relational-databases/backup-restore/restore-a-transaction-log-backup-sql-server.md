---
title: Restaurar una copia de seguridad de registros de transacciones (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675456"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="1bb7a-102">Restaurar una copia de seguridad de registros de transacciones (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bb7a-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="1bb7a-103">En este tema se describe cómo restaurar una copia de seguridad del registro de transacciones en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb7a-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1bb7a-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1bb7a-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1bb7a-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1bb7a-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1bb7a-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1bb7a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1bb7a-108">**Para restaurar una copia de seguridad del registro de transacciones, usando:**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="1bb7a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bb7a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1bb7a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bb7a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="1bb7a-111">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="1bb7a-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1bb7a-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1bb7a-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1bb7a-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1bb7a-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="1bb7a-114">Las copias de seguridad deben restaurarse en el mismo orden en el que se crearon.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="1bb7a-115">Para que pueda restaurar una copia de seguridad determinada del registro de transacciones, primero debe restaurar las siguientes copias de seguridad anteriores sin revertir las transacciones sin confirmar, es decir, WITH NORECOVERY:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="1bb7a-116">La copia de seguridad completa de la base de datos y la última copia de seguridad diferencial, si hay alguna, anteriores a la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="1bb7a-117">La base de datos debe haber utilizado el modelo de recuperación completa o el modelo de recuperación optimizado para cargas masivas de registros antes de crearse la copia de seguridad completa o diferencial más reciente.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="1bb7a-118">Todas las copias de seguridad de registros de transacciones realizadas después de la copia de seguridad completa o de la copia de seguridad diferencial (si restaura una) y antes de la copia de seguridad especificada del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="1bb7a-119">Las copias de seguridad de registros deben haberse aplicado en la secuencia en que fueron creadas, sin saltos en la cadena de registros.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="1bb7a-120">Para obtener más información sobre las copias de seguridad del registro de transacciones, vea [Copias de seguridad de registros de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) y [Aplicar copias de seguridad de registros de transacciones &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bb7a-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1bb7a-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1bb7a-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1bb7a-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="1bb7a-122">Permissions</span></span>  
 <span data-ttu-id="1bb7a-123">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="1bb7a-124">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1bb7a-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bb7a-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1bb7a-126">El proceso normal de una restauración consiste en seleccionar las copias de seguridad de registros en el cuadro de diálogo **Restaurar base de datos** junto con las copias de seguridad de datos y diferenciales.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="1bb7a-127">Para restaurar una copia de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="1bb7a-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="1bb7a-128">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1bb7a-129">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="1bb7a-130">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**, **Restaurar**y, después, haga clic en **Registro de transacciones**, con lo que se abre el cuadro de diálogo **Restaurar registro de transacciones** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bb7a-131">Si la opción **Registro de transacciones** está atenuada, es posible que primero deba restaurar una copia de seguridad completa o diferencial.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="1bb7a-132">Use el cuadro de diálogo de copia de seguridad **Base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="1bb7a-133">En el cuadro de lista **Base de datos** de la página **General** , seleccione el nombre de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="1bb7a-134">Solo aparecerán las bases de datos en estado de restauración.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="1bb7a-135">Para especificar el origen y la ubicación de los conjuntos de copias de seguridad que se deben restaurar, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="1bb7a-136">**Desde copias de seguridad de bases de datos anteriores**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="1bb7a-137">Seleccione la base de datos que desea restaurar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="1bb7a-138">La lista solo contiene las bases de datos de las que se han realizado copias de seguridad de acuerdo con el historial de copias de seguridad de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="1bb7a-139">**Desde archivo o cinta**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="1bb7a-140">Haga clic en el botón de exploración ( **...** ) para abrir el cuadro de diálogo **Seleccionar dispositivos de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="1bb7a-141">En el cuadro **Tipo de medio de copia de seguridad** , seleccione uno de los tipos de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="1bb7a-142">Para seleccionar uno o varios dispositivos del cuadro **Medio de copia de seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="1bb7a-143">Después de agregar los dispositivos que desee al cuadro de lista **Medio de copia de seguridad** , haga clic en **Aceptar** para volver a la página **General** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="1bb7a-144">En la cuadrícula **Seleccionar las copias de seguridad del registro de transacciones que se van a restaurar** , seleccione las copias de seguridad que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="1bb7a-145">En esta cuadrícula se muestran las copias de seguridad del registro de transacciones disponibles para la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="1bb7a-146">Una copia de seguridad del registro de transacciones solo está disponible si el **Primer LSN** es superior al **Último LSN** de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="1bb7a-147">Las copias de seguridad de registros aparecen en el orden de los números de secuencia de registro (LSN) que contienen y se deben restaurar en este orden.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="1bb7a-148">En la tabla siguiente se muestran los encabezados de columna de la cuadrícula y se describen sus valores.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="1bb7a-149">Encabezado</span><span class="sxs-lookup"><span data-stu-id="1bb7a-149">Header</span></span>|<span data-ttu-id="1bb7a-150">Value</span><span class="sxs-lookup"><span data-stu-id="1bb7a-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="1bb7a-151">**Restauración**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-151">**Restore**</span></span>|<span data-ttu-id="1bb7a-152">Las casillas seleccionadas indican los conjuntos de copias de seguridad que se restaurarán.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="1bb7a-153">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-153">**Name**</span></span>|<span data-ttu-id="1bb7a-154">Nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="1bb7a-155">**Componente**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-155">**Component**</span></span>|<span data-ttu-id="1bb7a-156">Componente cuya copia de seguridad se ha realizado: **Base de datos**, **Archivo** o \<blank> (para registros de transacciones).</span><span class="sxs-lookup"><span data-stu-id="1bb7a-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="1bb7a-157">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-157">**Database**</span></span>|<span data-ttu-id="1bb7a-158">Nombre de la base de datos que forma parte de la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="1bb7a-159">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-159">**Start Date**</span></span>|<span data-ttu-id="1bb7a-160">Fecha y hora de inicio de la operación de copia de seguridad, según la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="1bb7a-161">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-161">**Finish Date**</span></span>|<span data-ttu-id="1bb7a-162">Fecha y hora de finalización de la operación de copia de seguridad, según la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="1bb7a-163">**Primer LSN**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-163">**First LSN**</span></span>|<span data-ttu-id="1bb7a-164">Número de secuencia de registro de la primera transacción del conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="1bb7a-165">En blanco para las copias de seguridad de archivos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="1bb7a-166">**Último LSN**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-166">**Last LSN**</span></span>|<span data-ttu-id="1bb7a-167">Número de flujo de registro de la última transacción del conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="1bb7a-168">En blanco para las copias de seguridad de archivos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="1bb7a-169">**LSN de punto de comprobación**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="1bb7a-170">Número de flujo de registro del punto de comprobación más reciente en el momento en que se creó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="1bb7a-171">**LSN completo**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-171">**Full LSN**</span></span>|<span data-ttu-id="1bb7a-172">Número de secuencia de registro de la copia de seguridad completa más reciente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="1bb7a-173">**Server**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-173">**Server**</span></span>|<span data-ttu-id="1bb7a-174">Nombre de la instancia del motor de base de datos que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="1bb7a-175">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-175">**User Name**</span></span>|<span data-ttu-id="1bb7a-176">Nombre del usuario que realizó la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="1bb7a-177">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-177">**Size**</span></span>|<span data-ttu-id="1bb7a-178">Tamaño del conjunto de copias de seguridad, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="1bb7a-179">**Posición**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-179">**Position**</span></span>|<span data-ttu-id="1bb7a-180">Posición del conjunto de copias de seguridad en el volumen.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="1bb7a-181">**Expiración**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-181">**Expiration**</span></span>|<span data-ttu-id="1bb7a-182">Fecha y hora de expiración del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="1bb7a-183">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="1bb7a-184">**A un momento dado**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-184">**Point in time**</span></span>  
  
         <span data-ttu-id="1bb7a-185">Puede conservar el valor predeterminado (**Lo más reciente posible**) o seleccionar una fecha y hora determinadas haciendo clic en el botón Examinar, que abre el cuadro de diálogo **Restauración a un momento dado** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="1bb7a-186">**Transacción marcada**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="1bb7a-187">Restaura la base de datos al estado de una transacción previamente marcada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="1bb7a-188">Al seleccionar esta opción aparece el cuadro **Seleccionar transacción marcada** , en el que se muestra una cuadrícula con las transacciones marcadas disponibles en las copias de seguridad del registro de transacciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="1bb7a-189">De forma predeterminada, la restauración se realiza hasta la transacción marcada, sin incluirla.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="1bb7a-190">Para restaurar también la transacción marcada, seleccione **Incluir transacción marcada**.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="1bb7a-191">En la tabla siguiente se muestran los encabezados de columna de la cuadrícula y se describen sus valores.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="1bb7a-192">Encabezado</span><span class="sxs-lookup"><span data-stu-id="1bb7a-192">Header</span></span>|<span data-ttu-id="1bb7a-193">Value</span><span class="sxs-lookup"><span data-stu-id="1bb7a-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="1bb7a-194">Muestra una casilla para seleccionar la marca.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="1bb7a-195">**Marca de transacción**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-195">**Transaction Mark**</span></span>|<span data-ttu-id="1bb7a-196">Nombre de la transacción marcada especificada por el usuario cuando se confirmó la transacción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="1bb7a-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-197">**Date**</span></span>|<span data-ttu-id="1bb7a-198">Fecha y hora de confirmación de la transacción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="1bb7a-199">La fecha y hora de la transacción se muestran tal como están registradas en la tabla **msdbgmarkhistory** , no en la fecha y hora del equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="1bb7a-200">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-200">**Description**</span></span>|<span data-ttu-id="1bb7a-201">Descripción de la transacción marcada especificada por el usuario al confirmar la transacción (si la hay).</span><span class="sxs-lookup"><span data-stu-id="1bb7a-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="1bb7a-202">**LSN**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-202">**LSN**</span></span>|<span data-ttu-id="1bb7a-203">Número de flujo de registro de la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="1bb7a-204">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-204">**Database**</span></span>|<span data-ttu-id="1bb7a-205">Nombre de la base de datos en la que se confirmó la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="1bb7a-206">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-206">**User Name**</span></span>|<span data-ttu-id="1bb7a-207">Nombre del usuario de la base de datos que confirmó la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="1bb7a-208">Para ver o seleccionar las opciones avanzadas, haga clic en **Opciones** , en el panel **Seleccionar una página** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="1bb7a-209">En la sección **Opciones de restauración** , las opciones son:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="1bb7a-210">**Conservar la configuración de replicación (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="1bb7a-211">Conserva la configuración de replicación cuando se restaura una base de datos publicada en un servidor distinto de aquel en que se creó.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="1bb7a-212">Esta opción solo está disponible con la opción **dejar la base de datos lista para su uso revirtiendo las transacciones no confirmadas...** (descrita más adelante), que equivale a restaurar una copia de seguridad con la `RECOVERY` opción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="1bb7a-213">La activación de esta opción equivale a utilizar la `KEEP_REPLICATION` opción en una [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="1bb7a-214">**Preguntar antes de restaurar cada copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="1bb7a-215">Antes de restaurar cada conjunto de copia de seguridad (después del primero), esta opción abre el cuadro de diálogo **Continuar con la restauración** , en el que se solicita si quiere continuar con la secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="1bb7a-216">En este cuadro de diálogo se muestra el nombre del siguiente conjunto de medios (si lo hay), el nombre del conjunto de copias de seguridad y la descripción del conjunto de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="1bb7a-217">Esta opción resulta especialmente útil cuando se deben intercambiar cintas de distintos conjuntos de medios.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="1bb7a-218">Por ejemplo, se puede utilizar cuando el servidor solo dispone de un dispositivo de cinta.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="1bb7a-219">Espere hasta que esté listo para continuar antes de hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="1bb7a-220">Si hace clic en **No** , la base de datos se quedará en estado de restauración.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="1bb7a-221">Para mayor comodidad, puede continuar con la secuencia de restauración una vez completada la última restauración.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="1bb7a-222">Si la copia de seguridad siguiente es de datos o diferencial, vuelva a utilizar la tarea **Restaurar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="1bb7a-223">Si la siguiente copia de seguridad es una copia de seguridad de registros, utilice la tarea **Restaurar registro de transacciones** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="1bb7a-224">**Restringir el acceso a la base de datos restaurada (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="1bb7a-225">Hace que la base de datos restaurada esté disponible solo para los miembros de **db_owner**, **dbcreator**o **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="1bb7a-226">La activación de esta opción equivale al uso `RESTRICTED_USER` de la opción en una [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="1bb7a-227">Para las opciones **Estado de recuperación** , especifique el estado de la base de datos después de la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="1bb7a-228">**Revertir las transacciones no confirmadas para dejar la base de datos lista para su uso. No pueden restaurarse registros de transacciones adicionales. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="1bb7a-229">Recupera la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-229">Recovers the database.</span></span> <span data-ttu-id="1bb7a-230">Esta opción es equivalente a la `RECOVERY` opción en una [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="1bb7a-231">Elíjala solo si no desea restaurar ningún archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="1bb7a-232">**Dejar la base de datos no operativa y no revertir las transacciones no confirmadas. Pueden restaurarse registros de transacciones adicionales. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="1bb7a-233">Deja la base de datos sin recuperar, en el estado `RESTORING`.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="1bb7a-234">Esta opción es equivalente a usar la `NORECOVERY` opción en una [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="1bb7a-235">Si elige esta opción, la opción **Conservar la configuración de replicación** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1bb7a-236">Para un reflejo o una base de datos secundaria, seleccione siempre esta opción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="1bb7a-237">**Dejar la base de datos en modo de solo lectura. Deshacer las transacciones sin confirmar, pero guardar las acciones de deshacer en un archivo para que los efectos de recuperación puedan invertirse. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="1bb7a-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="1bb7a-238">Deja la base de datos en estado de espera.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="1bb7a-239">Esta opción es equivalente a usar la `STANDBY` opción en una [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="1bb7a-240">Si elige esta opción, debe especificar un archivo en espera.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="1bb7a-241">O bien, especifique un nombre de archivo en espera en el cuadro de texto **Archivo en espera** .</span><span class="sxs-lookup"><span data-stu-id="1bb7a-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="1bb7a-242">Esta opción es obligatoria si se deja la base de datos en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="1bb7a-243">Puede buscar el archivo en espera o escribir su ruta de acceso en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1bb7a-244">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bb7a-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1bb7a-245">Se recomienda que especifique siempre WITH NORECOVERY o WITH RECOVERY en todas las instrucciones RESTORE para evitar ambigüedades.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="1bb7a-246">Esto es especialmente importante cuando se escriben scripts.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="1bb7a-247">Para restaurar una copia de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="1bb7a-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="1bb7a-248">Ejecute la instrucción RESTORE LOG para aplicar la copia de seguridad del registro de transacciones especificando:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="1bb7a-249">El nombre de la base de datos a la que se aplicará el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="1bb7a-250">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="1bb7a-251">La cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="1bb7a-252">La sintaxis básica de esta instrucción es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="1bb7a-253">RESTORE LOG *nombre_de_base_de_datos* FROM <dispositivo_de_copia_de_seguridad> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="1bb7a-254">Donde *nombre_de_base_de_datos* es el nombre de la base de datos y <dispositivo_de_copia_de_seguridad> es el nombre del dispositivo que contiene la copia de seguridad de registros que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="1bb7a-255">Repita el paso 1 para cada copia de seguridad del registro de transacciones que tenga que aplicar.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="1bb7a-256">Después de restaurar la copia de seguridad más reciente en la secuencia de restauración, use una de las instrucciones siguientes para recuperar la base de datos:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="1bb7a-257">Recuperar la base de datos como parte de la última instrucción RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="1bb7a-258">Esperar a recuperar la base de datos utilizando otra instrucción RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="1bb7a-259">Si espera a recuperar la base de datos tendrá la oportunidad de comprobar que ha restaurado todas las copias de seguridad de registros necesarias.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="1bb7a-260">Este método suele ser aconsejable al realizar restauraciones a un momento dado.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1bb7a-261">Si está creando una base de datos reflejada, omita el paso de recuperación.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="1bb7a-262">Una base de datos reflejada debe permanecer en el estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1bb7a-263">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bb7a-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="1bb7a-264">La base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] usa el modelo de recuperación simple de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="1bb7a-265">En los siguientes ejemplos se requiere la modificación de la base de datos para utilizar el modelo de recuperación completa, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1bb7a-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="1bb7a-266">A.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-266">A.</span></span> <span data-ttu-id="1bb7a-267">Aplicar una sola copia de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="1bb7a-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="1bb7a-268">En el siguiente ejemplo se empieza con la restauración de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] utilizando una copia de seguridad completa de la base de datos que se encuentra en un dispositivo de copia de seguridad denominado `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="1bb7a-269">A continuación, se aplica la primera copia de seguridad del registro de transacciones, que se encuentra en un dispositivo de copia de seguridad denominado `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="1bb7a-270">Finalmente, el ejemplo recupera la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="1bb7a-271">B.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-271">B.</span></span> <span data-ttu-id="1bb7a-272">Aplicar varias copias de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="1bb7a-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="1bb7a-273">En el siguiente ejemplo se empieza con la restauración de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] utilizando una copia de seguridad completa de la base de datos que se encuentra en un dispositivo de copia de seguridad denominado `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="1bb7a-274">A continuación, se aplican, una por una, las tres primeras copias de seguridad del registro de transacciones, que se encuentran en un dispositivo de copia de seguridad denominado `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="1bb7a-275">Finalmente, el ejemplo recupera la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb7a-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1bb7a-276">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="1bb7a-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1bb7a-277">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="1bb7a-278">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="1bb7a-279">Restaurar una base de datos según el punto de error en el modelo de recuperación completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="1bb7a-280">Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="1bb7a-281">Restaurar una base de datos en una transacción marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bb7a-282">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bb7a-282">See Also</span></span>  
 <span data-ttu-id="1bb7a-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1bb7a-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="1bb7a-284">Aplicar copias de seguridad de registros de transacción &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1bb7a-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
