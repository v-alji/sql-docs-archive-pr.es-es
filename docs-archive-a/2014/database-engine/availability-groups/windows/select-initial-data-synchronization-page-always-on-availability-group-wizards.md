---
title: Página seleccionar sincronización de datos iniciales (asistentes para grupos de disponibilidad AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.selectinitialdatasync.f1
- sql12.swb.adddatabasewizard.selectinitialdatasync.f1
- sql12.swb.newagwizard.selectinitialdatasync.f1
ms.assetid: 457b1140-4819-4def-8f7c-54a406e6db12
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f7d8fbe6f885136e030c80719f2e16d1c689f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749485"
---
# <a name="select-initial-data-synchronization-page-alwayson-availability-group-wizards"></a><span data-ttu-id="37f09-102">Página Seleccionar sincronización de datos iniciales (asistentes para grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="37f09-102">Select Initial Data Synchronization Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="37f09-103">Use la página de AlwaysOn **Seleccionar sincronización de datos iniciales** para indicar sus preferencias para la sincronización de datos inicial de las nuevas bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="37f09-103">Use the AlwaysOn **Select Initial Data Synchronization** page to indicate your preference for initial data synchronization of new secondary databases.</span></span> <span data-ttu-id="37f09-104">Esta página es compartida por tres asistentes: [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], el [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] y el [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f09-104">This page is shared by three wizards-the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and the [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)].</span></span>  
  
 <span data-ttu-id="37f09-105">Las opciones posibles son **Completa**, **Solo unión**u **Omitir la sincronización de datos iniciales**.</span><span class="sxs-lookup"><span data-stu-id="37f09-105">The possible choices include **Full**, **Join only**, or **Skip initial data synchronization**.</span></span> <span data-ttu-id="37f09-106">Antes de seleccionar **Completa** o **Solo unión** asegúrese de que el entorno cumpla los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="37f09-106">Before you select **Full** or **Join only** ensure that your environment meets the prerequisites.</span></span>  
  

  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="37f09-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="37f09-107">Recommendations</span></span>  
  
-   <span data-ttu-id="37f09-108">Suspenda las tareas de copia de seguridad de registros para las bases de datos principales durante la sincronización de datos inicial.</span><span class="sxs-lookup"><span data-stu-id="37f09-108">Suspend log backup tasks for the primary databases during initial data synchronization.</span></span>  
  
-   <span data-ttu-id="37f09-109">Para una base de datos grande, las operaciones de copias de seguridad y restauración completa pueden tardar mucho tiempo y consumir gran cantidad de recursos extensos.</span><span class="sxs-lookup"><span data-stu-id="37f09-109">For large database, full backup and restore operations can take extensive time and resources.</span></span> <span data-ttu-id="37f09-110">En esos casos, se recomienda que usted mismo prepare las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="37f09-110">In such cases, we recommend that you prepare secondary databases yourself.</span></span> <span data-ttu-id="37f09-111">Para obtener más información, vea [Para preparar las bases de datos secundarias manualmente](#PrepareSecondaryDbs), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="37f09-111">For more information, see [To Prepare Secondary Databases Manually](#PrepareSecondaryDbs), later in this topic.</span></span>  
  
-   <span data-ttu-id="37f09-112">La sincronización de datos inicial completa requiere especificar un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-112">Full initial data synchronization requires you to specify a network share.</span></span> <span data-ttu-id="37f09-113">Antes de utilizar un asistente para realizar la sincronización de datos iniciales completa, se recomienda implementar un plan de seguridad para los permisos de acceso en la carpeta del recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-113">Before you use a wizard to perform full initial data synchronization, we recommend that you implement a security plan for the access permissions on the network share folder.</span></span> <span data-ttu-id="37f09-114">Esta precaución es importante porque cualquiera que tenga un permiso de lectura (READ) en la carpeta puede tener acceso datos potencialmente datos confidenciales del archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37f09-114">This precaution is important because potentially sensitive data in the backup file can be accessed by anyone who has a READ permission on the folder.</span></span> <span data-ttu-id="37f09-115">Además, para proteger su operaciones de copias de seguridad y restauración, se recomienda proteger los canales de red entre todas las instancias de servidor que hospedan una réplica de disponibilidad y la carpeta del recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-115">Also, to protect your backup and restore operations, we recommend that you secure the network channels between every server instance that hosts an availability replica and the network share folder.</span></span>  
  
     <span data-ttu-id="37f09-116">Si las operaciones de copia de seguridad y restauración deben estar muy protegidas, se recomienda seleccionar la opción **Solo unión** u **Omitir la sincronización de datos iniciales** .</span><span class="sxs-lookup"><span data-stu-id="37f09-116">If your backup and restore operations must be highly secured, we recommend that you select either the **Join only** or **Skip initial data synchronization** option.</span></span>  
  
##  <a name="full"></a><a name="Full"></a><span data-ttu-id="37f09-117">Total</span><span class="sxs-lookup"><span data-stu-id="37f09-117">Full</span></span>  
 <span data-ttu-id="37f09-118">Para cada base de datos principal, la opción **Completa** realiza varias operaciones en un flujo de trabajo: crear una copia de seguridad completa y de registros de la base de datos principal, crear las bases de datos secundarias correspondientes restaurando estas copias de seguridad en cada instancia de servidor que está hospedando una réplica secundaria y unir cada base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-118">For each primary database, the **Full** option performs several operations in one workflow:  create a full and log backup of the primary database, create the corresponding secondary databases by restoring these backups on every server instance that is hosting a secondary replica, and join each secondary database to availability group.</span></span>  
  
 <span data-ttu-id="37f09-119">Seleccione esta opción solo si su entorno cumple los requisitos previos para utilizar la sincronización de datos inicial completa y desea que el asistente inicie automáticamente la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="37f09-119">Select this option only if your environment meets the following prerequisites for using full initial data synchronization, and you want the wizard to automatically start data synchronization.</span></span>  
  
 <span data-ttu-id="37f09-120">**Requisitos previos para usar la sincronización de datos inicial completa**</span><span class="sxs-lookup"><span data-stu-id="37f09-120">**Prerequisites for using full initial data synchronization**</span></span>  
  
-   <span data-ttu-id="37f09-121">Todas las rutas de acceso de archivos de base de datos deben ser idénticas en todas las instancias de servidor que hospedan una réplica para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-121">All the database-file paths must be identical on every server instance that hosts a replica for the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37f09-122">Si las rutas de acceso de copias de seguridad y restauración difieren entre la instancia del servidor donde se ejecuta el asistente y cualquier instancia de servidor que vaya a hospedar una replicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="37f09-122">If the backup and restore file paths differ between the server instance where you run the wizard and any server instance that is to host a secondary replica.</span></span> <span data-ttu-id="37f09-123">Las operaciones de copia de seguridad y restauración deben realizarse manualmente mediante la opción MOVE.</span><span class="sxs-lookup"><span data-stu-id="37f09-123">The backup and restore operations must be performed manually using the WITH MOVE option.</span></span> <span data-ttu-id="37f09-124">Para obtener más información, vea [Para preparar las bases de datos secundarias manualmente](#PrepareSecondaryDbs), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="37f09-124">For more information, see [To Prepare Secondary Databases Manually](#PrepareSecondaryDbs), later in this topic.</span></span>  
  
-   <span data-ttu-id="37f09-125">Ningún nombre de base de datos principal puede existir en ninguna instancia de servidor que hospede una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="37f09-125">No primary database name can exist on any server instance that hosts a secondary replica.</span></span> <span data-ttu-id="37f09-126">Esto significa que ninguna de las nuevas bases de datos secundarias puede existir todavía.</span><span class="sxs-lookup"><span data-stu-id="37f09-126">This means that none of the new secondary databases can exist yet.</span></span>  
  
-   <span data-ttu-id="37f09-127">Tendrá que especificar un recurso compartido de red para que el asistente cree y obtenga acceso a las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37f09-127">You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="37f09-128">Para la réplica principal, la cuenta usada para iniciar el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] debe tener permisos del sistema de archivos de lectura y escritura en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-128">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="37f09-129">Para las réplicas secundarias, la cuenta debe tener permiso de lectura en el recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-129">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="37f09-130">Las copias de seguridad de registros serán parte de la cadena de copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="37f09-130">The log backups will be part of your log backup chain.</span></span> <span data-ttu-id="37f09-131">Almacene adecuadamente los archivos de copia de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="37f09-131">Store the log backup files appropriately.</span></span>  
  
 <span data-ttu-id="37f09-132">**Si los requisitos previos no se cumplen**</span><span class="sxs-lookup"><span data-stu-id="37f09-132">**If prerequisites are not met**</span></span>  
  
 <span data-ttu-id="37f09-133">El asistente no puede crear las bases de datos secundarias para este grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-133">The wizard cannot create the secondary databases for this availability group.</span></span> <span data-ttu-id="37f09-134">Para obtener información sobre cómo prepararlas, vea [Para preparar las bases de datos secundarias manualmente](#PrepareSecondaryDbs), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="37f09-134">For information on how to prepare them, see [To Prepare Secondary Databases Manually](#PrepareSecondaryDbs), later in this topic.</span></span>  
  
 <span data-ttu-id="37f09-135">**Si los requisitos previos se cumplen**</span><span class="sxs-lookup"><span data-stu-id="37f09-135">**If prerequisites are met**</span></span>  
  
 <span data-ttu-id="37f09-136">Si todos estos requisitos previos se cumplen y desea que el asistente realice la sincronización de datos inicial completa, seleccione la opción **Completo** y especifique un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-136">If these prerequisites are all met and you want the wizard to perform full initial data synchronization, select the **Full** option and specify a network share.</span></span> <span data-ttu-id="37f09-137">Esto hará que el asistente cree la base de datos completa y de registros de cada base de datos seleccionada y coloque estas copias de seguridad en el recurso compartido de red que especifique.</span><span class="sxs-lookup"><span data-stu-id="37f09-137">This will cause  the wizard to create full database and log backups of every selected database and to place these backups on the network share that you specify.</span></span> <span data-ttu-id="37f09-138">Después, en cada instancia de servidor que hospeda una de las nuevas réplicas secundarias, el asistente creará las bases de datos secundarias restaurando las copias de seguridad utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="37f09-138">Then, on every server instance that hosts one of the new secondary replicas, the wizard will create the secondary databases by restoring backups using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="37f09-139">Después de crear cada una de las bases de datos secundarias, el asistente unirá la nueva base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-139">After creating each of the secondary databases, the wizard will join the new secondary database to the availability group.</span></span> <span data-ttu-id="37f09-140">En cuanto se une una base de datos secundaria, se inician las sincronizaciones de datos en ella.</span><span class="sxs-lookup"><span data-stu-id="37f09-140">As soon as a secondary database is joined, data synchronizations starts on that database.</span></span>  
  
 <span data-ttu-id="37f09-141">**Especifique una ubicación de red compartida accesible por todas las réplicas**</span><span class="sxs-lookup"><span data-stu-id="37f09-141">**Specify a shared network location accessible by all replicas**</span></span>  
 <span data-ttu-id="37f09-142">Para crear y restaurar copias de seguridad, el asistente requiere que se especifique un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-142">To create and restore backups, the wizard requires that you specify a network share.</span></span> <span data-ttu-id="37f09-143">La cuenta utilizada para iniciar [!INCLUDE[ssDE](../../../includes/ssde-md.md)] en cada instancia de servidor que hospedará una réplica de disponibilidad debe tener permisos de sistema de archivos de lectura/escritura en el recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="37f09-143">The account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] on each server instance that will host an availability replica must have read and write file-system permissions on the network share.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37f09-144">Las copias de seguridad de registros serán parte de la cadena de copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="37f09-144">The log backups will be part of your log backup chain.</span></span> <span data-ttu-id="37f09-145">Almacene adecuadamente los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37f09-145">Store their backup files appropriately.</span></span>  
  
##  <a name="join-only"></a><a name="Joinonly"></a><span data-ttu-id="37f09-146">Solo unirse</span><span class="sxs-lookup"><span data-stu-id="37f09-146">Join only</span></span>  
 <span data-ttu-id="37f09-147">Seleccione esta opción solo si las nuevas bases de datos secundarias ya existen en cada instancia de servidor que hospeda una réplica secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-147">Select this option only if the new secondary databases already exist on each server instance that hosts a secondary replica for the availability group.</span></span> <span data-ttu-id="37f09-148">Para obtener información sobre cómo preparar las bases de datos secundarias, vea la sección [Para preparar las bases de datos secundarias manualmente](#PrepareSecondaryDbs), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="37f09-148">For information about preparing secondary databases, see [To Prepare Secondary Databases Manually](#PrepareSecondaryDbs), later in this section.</span></span>  
  
 <span data-ttu-id="37f09-149">Si selecciona **Solo unión**, el asistente intentará unir cada base de datos secundaria existente al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-149">If you select **Join only**, the wizard will attempt to join each existing secondary database to the availability group.</span></span>  
  
## <a name="skip-initial-data-synchronization"></a><span data-ttu-id="37f09-150">Omitir la sincronización de datos iniciales</span><span class="sxs-lookup"><span data-stu-id="37f09-150">Skip initial data synchronization</span></span>  
 <span data-ttu-id="37f09-151">Seleccione esta opción si desea realizar sus propias copias de seguridad de bases de datos y registros de cada base de datos principal, y restaurarlas en cada instancia del servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="37f09-151">Select this option if you want to perform your own database and log backups of every primary database, restore them to every server instance that hosts a secondary replica.</span></span> <span data-ttu-id="37f09-152">Después de salir del asistente, tendrá que unir todas las base de datos secundaria en todas las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="37f09-152">After you exit the wizard, you will then need to join every secondary database on every secondary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37f09-153">Para más información, vea [Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37f09-153">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="to-prepare-secondary-databases-manually"></a><a name="PrepareSecondaryDbs"></a><span data-ttu-id="37f09-154">Para preparar las bases de datos secundarias manualmente</span><span class="sxs-lookup"><span data-stu-id="37f09-154">To Prepare Secondary Databases Manually</span></span>  
 <span data-ttu-id="37f09-155">Para preparar las bases de datos secundarias independientemente de cualquier asistente de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , puede utilizar cualquiera de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="37f09-155">To prepare secondary databases independently of any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard, you can use either of the following approaches:</span></span>  
  
-   <span data-ttu-id="37f09-156">Restaure manualmente una copia de seguridad reciente de la base de datos principal utilizando RESTORE WITH NORECOVERY y restaure después cada copia de seguridad de registros posterior utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="37f09-156">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="37f09-157">Si las bases de datos principal y secundaria tienen distintas rutas de acceso, debe utilizar la opción WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="37f09-157">If the primary and secondary databases have different file paths, you must use the WITH MOVE option.</span></span> <span data-ttu-id="37f09-158">Realice esta secuencia de restauración en cada instancia del servidor que hospeda una réplica secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-158">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  <span data-ttu-id="37f09-159">Puede utilizar [!INCLUDE[tsql](../../../includes/tsql-md.md)] o PowerShell para realizar este operaciones de copias de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="37f09-159">You can use [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell to perform these backup and restore operations.</span></span>  
  
     <span data-ttu-id="37f09-160">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="37f09-160">**For more information:**</span></span>  
  
     [<span data-ttu-id="37f09-161">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-161">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   <span data-ttu-id="37f09-162">Si va a agregar una o varias bases de datos principales de trasvase de registros en un grupo de disponibilidad, es posible que pueda migrar una o varias de sus bases de datos secundarias correspondientes de los grupos de trasvase de registros a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f09-162">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="37f09-163">Para obtener más información, consulte [requisitos previos para migrar desde el trasvase de registros a Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="37f09-163">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37f09-164">Después de crear todas las bases de datos secundarias para el grupo de disponibilidad, si desea realizar copias de seguridad en las réplicas secundarias, deberá configurar de nuevo la preferencia de copia de seguridad automatizada del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-164">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
     <span data-ttu-id="37f09-165">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="37f09-165">**For more information:**</span></span>  
  
     [<span data-ttu-id="37f09-166">Requisitos previos para la migración desde el trasvase de registros a Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-166">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
     [<span data-ttu-id="37f09-167">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-167">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="37f09-168">Después de crear una base de datos secundaria, aplíquele todas las copias de seguridad de registros actuales.</span><span class="sxs-lookup"><span data-stu-id="37f09-168">After creating a secondary database, apply all current log backups to the new secondary database.</span></span>  
  
 <span data-ttu-id="37f09-169">Opcionalmente, puede preparar todas las bases de datos secundarias antes de ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="37f09-169">Optionally, you can prepare all the secondary databases before you run the wizard.</span></span> <span data-ttu-id="37f09-170">Entonces, en la página **Especificar la sincronización de datos iniciales** del asistente, seleccione **Solo unión** para unir automáticamente las nuevas bases de datos secundarias al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="37f09-170">Then, on the wizard's **Specify Initial Data Synchronization** page, select **Join only** to automatically join your new secondary databases to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="37f09-171">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="37f09-171">Related Tasks</span></span>  
  
-   [<span data-ttu-id="37f09-172">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-172">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="37f09-173">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-173">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="37f09-174">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-174">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="37f09-175">Usar el Asistente para grupo de disponibilidad de conmutación por error &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-175">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="37f09-176">Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-176">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="37f09-177">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-177">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="37f09-178">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-178">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="37f09-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37f09-179">See Also</span></span>  
 [<span data-ttu-id="37f09-180">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f09-180">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  