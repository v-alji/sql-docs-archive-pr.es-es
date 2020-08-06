---
title: Acerca del trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745393"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="45251-102">Acerca del trasvase de registros (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="45251-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="45251-103">El trasvase de registros permite enviar automáticamente copias de seguridad del registro de transacciones desde una *base de datos principal* de una instancia del *servidor principal* a una o varias *bases de datos secundarias* en instancias independientes del *servidor secundario* .</span><span class="sxs-lookup"><span data-stu-id="45251-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="45251-104">Las copias de seguridad del registro de transacciones se aplican a cada una de las bases de datos secundarias de forma individual.</span><span class="sxs-lookup"><span data-stu-id="45251-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="45251-105">En una tercera instancia de servidor opcional, denominado *servidor de supervisión*, se registra el historial y el estado de las operaciones de copias de seguridad y restauración y, opcionalmente, se activan alertas si estas operaciones no se producen según lo programado.</span><span class="sxs-lookup"><span data-stu-id="45251-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="45251-106">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="45251-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="45251-107">Ventajas</span><span class="sxs-lookup"><span data-stu-id="45251-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="45251-108">Términos y definiciones</span><span class="sxs-lookup"><span data-stu-id="45251-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="45251-109">Información general de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="45251-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="45251-110">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="45251-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="45251-111">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="45251-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="45251-112">Ventajas</span><span class="sxs-lookup"><span data-stu-id="45251-112">Benefits</span></span>  
  
-   <span data-ttu-id="45251-113">Proporciona una solución de recuperación ante desastres para una sola base de datos principal y una o más bases de datos secundarias, cada una en una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45251-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="45251-114">Admite acceso limitado de solo lectura a bases de datos secundarias (durante el intervalo entre los trabajos de restauración).</span><span class="sxs-lookup"><span data-stu-id="45251-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="45251-115">Permite un retraso especificado por el usuario entre el momento en que el servidor principal realiza una copia de seguridad del registro de la base de datos principal y el momento en que los servidores secundarios deben restaurar (aplicar) la copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="45251-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="45251-116">Un retraso más largo puede ser útil, por ejemplo, si los datos se cambian en la base de datos principal de manera accidental.</span><span class="sxs-lookup"><span data-stu-id="45251-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="45251-117">Si se detecta rápidamente el cambio accidental, un retraso puede permitirle recuperar los datos aún sin modificar de una base de datos secundaria antes de que el cambio se refleje en ella.</span><span class="sxs-lookup"><span data-stu-id="45251-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="45251-118">Términos y definiciones</span><span class="sxs-lookup"><span data-stu-id="45251-118">Terms and Definitions</span></span>  
 <span data-ttu-id="45251-119">servidor principal</span><span class="sxs-lookup"><span data-stu-id="45251-119">primary server</span></span>  
 <span data-ttu-id="45251-120">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que es el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="45251-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="45251-121">base de datos principal</span><span class="sxs-lookup"><span data-stu-id="45251-121">primary database</span></span>  
 <span data-ttu-id="45251-122">La base de datos del servidor principal de la que desea realizar una copia de seguridad en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="45251-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="45251-123">Toda la administración de la configuración de trasvase de registros mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] se realiza en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="45251-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="45251-124">servidor secundario</span><span class="sxs-lookup"><span data-stu-id="45251-124">secondary server</span></span>  
 <span data-ttu-id="45251-125">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde desea mantener una copia en estado de espera activa de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="45251-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="45251-126">base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="45251-126">secondary database</span></span>  
 <span data-ttu-id="45251-127">La copia en estado de espera activa de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="45251-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="45251-128">La base de datos secundaria debe encontrarse en el estado RECOVERING o STANDBY, que deja la base de datos disponible para acceso limitado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="45251-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="45251-129">servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="45251-129">monitor server</span></span>  
 <span data-ttu-id="45251-130">Una instancia opcional de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que realiza un seguimiento de todos los detalles del trasvase de registros, como:</span><span class="sxs-lookup"><span data-stu-id="45251-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="45251-131">Cuándo se realizó por última vez una copia de seguridad del registro de transacciones de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="45251-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="45251-132">Cuándo se realizó por última vez la copia y restauración de los archivos de copia de seguridad en los servidores secundarios.</span><span class="sxs-lookup"><span data-stu-id="45251-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="45251-133">Información acerca de las alertas de error de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="45251-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45251-134">Una vez configurado el servidor de supervisión, no puede modificarse sin quitar primero el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="45251-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="45251-135">trabajo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="45251-135">backup job</span></span>  
 <span data-ttu-id="45251-136">Un trabajo del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que lleva a cabo la operación de copia de seguridad, registra el historial en el servidor local y el servidor de supervisión, y elimina los archivos de copia de seguridad y la información de historial antiguos.</span><span class="sxs-lookup"><span data-stu-id="45251-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="45251-137">La categoría de trabajo "Copia de seguridad de trasvase de registros" se crea en la instancia del servidor principal al habilitar el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="45251-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="45251-138">trabajo de copia</span><span class="sxs-lookup"><span data-stu-id="45251-138">copy job</span></span>  
 <span data-ttu-id="45251-139">Un trabajo del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que copia los archivos de copia de seguridad del servidor principal en un destino configurable del servidor secundario y registra el historial en el servidor secundario y el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="45251-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="45251-140">La categoría de trabajo "Copia de seguridad de trasvase de registros" se crea en cada servidor secundario en una configuración de trasvase de registros al habilitar el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="45251-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="45251-141">trabajo de restauración</span><span class="sxs-lookup"><span data-stu-id="45251-141">restore job</span></span>  
 <span data-ttu-id="45251-142">Un trabajo del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que restaura los archivos de copia de seguridad copiados en las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="45251-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="45251-143">Registra el historial en el servidor local y el servidor de supervisión, y elimina los archivos de copia de seguridad y la información de historial antiguos.</span><span class="sxs-lookup"><span data-stu-id="45251-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="45251-144">La categoría de trabajo "Restauración de trasvase de registros" se crea en la instancia del servidor secundario al habilitar el trasvase de registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="45251-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="45251-145">trabajo de alerta</span><span class="sxs-lookup"><span data-stu-id="45251-145">alert job</span></span>  
 <span data-ttu-id="45251-146">Un trabajo del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que activa alertas para las bases de datos principal y secundaria cuando una operación de copia de seguridad o restauración no se completa correctamente según un umbral especificado.</span><span class="sxs-lookup"><span data-stu-id="45251-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="45251-147">La categoría de trabajo "Alerta de trasvase de registros" se crea en la instancia del servidor de supervisión al habilitar el trasvase de registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="45251-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="45251-148">Para cada alerta, debe especificar un número de alerta.</span><span class="sxs-lookup"><span data-stu-id="45251-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="45251-149">Además, asegúrese de configurar la alerta para notificar a un operador cuándo se activa una alerta.</span><span class="sxs-lookup"><span data-stu-id="45251-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="45251-150">Información general de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="45251-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="45251-151">El trasvase de registros consta de tres operaciones:</span><span class="sxs-lookup"><span data-stu-id="45251-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="45251-152">Realizar una copia de seguridad del registro de transacciones en la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="45251-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="45251-153">Copiar el archivo de registro de transacciones en la instancia del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="45251-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="45251-154">Restaurar la copia de seguridad de registros en la instancia del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="45251-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="45251-155">El registro se puede trasvasar a varias instancias del servidor secundario</span><span class="sxs-lookup"><span data-stu-id="45251-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="45251-156">En ese caso, las operaciones 2 y 3 se repiten para cada instancia del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="45251-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="45251-157">En una configuración de trasvase de registros no se realiza automáticamente la conmutación por error del servidor principal al servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="45251-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="45251-158">Si la base de datos principal deja de estar disponible, cualquiera de las bases de datos secundarias se puede poner en línea manualmente.</span><span class="sxs-lookup"><span data-stu-id="45251-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="45251-159">Puede utilizar una base de datos secundaria para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="45251-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="45251-160">Además, puede configurar alertas para la configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="45251-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="45251-161">Una configuración de trasvase de registros típica</span><span class="sxs-lookup"><span data-stu-id="45251-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="45251-162">La siguiente ilustración muestra una configuración de trasvase de registros con la instancia del servidor principal, tres instancias del servidor secundario y una instancia del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="45251-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="45251-163">La ilustración presenta los pasos realizados por los trabajos de copia de seguridad, copia y restauración del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="45251-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="45251-164">La instancia del servidor principal ejecuta el trabajo de copia de seguridad del registro de transacciones en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="45251-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="45251-165">A continuación, esta instancia de servidor coloca la copia de seguridad del registro en un archivo principal de copias de seguridad de registros que se envía a la carpeta de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="45251-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="45251-166">En esta ilustración, la carpeta de copia de seguridad es un directorio compartido: el *recurso compartido de copia de seguridad*.</span><span class="sxs-lookup"><span data-stu-id="45251-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="45251-167">Cada una de las tres instancias del servidor secundario ejecuta su propio trabajo de copia para copiar el archivo principal de copia de seguridad de registros a su propia carpeta de destino local.</span><span class="sxs-lookup"><span data-stu-id="45251-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="45251-168">Cada instancia del servidor secundario ejecuta su propio trabajo de restauración para restaurar la copia de seguridad del registro desde la carpeta de destino local a la base de datos secundaria local.</span><span class="sxs-lookup"><span data-stu-id="45251-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="45251-169">Las instancias del servidor principal y secundario envían su propio historial y estado a la instancia del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="45251-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="45251-170">![Configuración que muestra trabajos de copia de seguridad, copia y restauración](../media/ls-typical-configuration.gif "Configuración que muestra trabajos de copia de seguridad, copia y restauración")</span><span class="sxs-lookup"><span data-stu-id="45251-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="45251-171">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="45251-171">Interoperability</span></span>  
 <span data-ttu-id="45251-172">El trasvase de registros se puede usar con las siguientes características o componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="45251-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="45251-173">Requisitos previos para la migración desde el trasvase de registros a Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="45251-174">Crear reflejo de la base de datos y trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="45251-175">Trasvase de registros y replicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="45251-176">y la creación de reflejo de la base de datos son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="45251-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="45251-177">Una base de datos configurada para una de estas características no puede configurarse para la otra.</span><span class="sxs-lookup"><span data-stu-id="45251-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="45251-178">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="45251-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="45251-179">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="45251-180">Configurar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="45251-181">Agregar una base de datos secundaria a la configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="45251-182">Quitar una base de datos secundaria desde una configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="45251-183">Quitar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="45251-184">Ver el informe de trasvase de registros &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="45251-185">Supervisar el trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="45251-186">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="45251-187">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="45251-188">Administración de inicios de sesión y trabajos tras la conmutación de roles &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="45251-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45251-189">See Also</span></span>  
 [<span data-ttu-id="45251-190">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45251-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
