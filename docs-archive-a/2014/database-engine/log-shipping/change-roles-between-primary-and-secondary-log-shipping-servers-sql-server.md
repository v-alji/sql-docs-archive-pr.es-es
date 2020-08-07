---
title: Cambiar los roles entre el servidor de trasvase de registros primario y secundario (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747169"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="d1f16-102">Cambiar los roles entre el servidor de trasvase de registros primario y secundario (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d1f16-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="d1f16-103">Después de haber realizado la conmutación por error de una configuración de trasvase de registros de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un servidor secundario, puede configurar la base de datos secundaria para que actúe como base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="d1f16-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="d1f16-104">De este modo, podrá intercambiar la base de datos primaria y la secundaria cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d1f16-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="d1f16-105">Realizar el cambio de rol inicial</span><span class="sxs-lookup"><span data-stu-id="d1f16-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="d1f16-106">La primera vez que desee conmutar por error a una base de datos secundaria para convertirla en su nueva base de datos principal, debe realizar una serie de pasos.</span><span class="sxs-lookup"><span data-stu-id="d1f16-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="d1f16-107">Una vez realizados, podrá intercambiar fácilmente los roles entre la base de datos principal y la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="d1f16-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="d1f16-108">Realice manualmente la conmutación por error de la base de datos principal a la secundaria.</span><span class="sxs-lookup"><span data-stu-id="d1f16-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="d1f16-109">Asegúrese de realizar una copia de seguridad del registro de transacciones activo en su servidor principal mediante NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d1f16-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="d1f16-110">Para obtener más información, vea [Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1f16-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d1f16-111">Deshabilite el trabajo de copia de seguridad de trasvase de registros en el servidor principal, así como los trabajos de copia y restauración en el servidor secundario original.</span><span class="sxs-lookup"><span data-stu-id="d1f16-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d1f16-112">En la base de datos secundaria (la que desea convertir en principal), configure el trasvase de registros mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1f16-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d1f16-113">Para obtener más información, vea [Configurar el trasvase de registros &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1f16-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="d1f16-114">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d1f16-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="d1f16-115">Utilice el mismo recurso compartido para crear copias de seguridad que el utilizado para el servidor principal original.</span><span class="sxs-lookup"><span data-stu-id="d1f16-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="d1f16-116">Cuando agregue la base de datos secundaria, en el cuadro de diálogo **Configuración de base de datos secundaria** , escriba el nombre de la base de datos principal original en el cuadro **Base de datos secundaria** .</span><span class="sxs-lookup"><span data-stu-id="d1f16-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="d1f16-117">En el cuadro de diálogo **Configuración de base de datos secundaria** , seleccione **No, la base de datos secundaria está inicializada**.</span><span class="sxs-lookup"><span data-stu-id="d1f16-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="d1f16-118">Si la supervisión del trasvase de registros estaba habilitada en la anterior configuración de trasvase de registros, vuelva a configurarla para supervisar la nueva configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="d1f16-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="d1f16-119">Ejecute los siguientes comandos, y reemplace *database_name* por el nombre de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="d1f16-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="d1f16-120">**En el nuevo servidor principal**</span><span class="sxs-lookup"><span data-stu-id="d1f16-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="d1f16-121">Ejecute las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1f16-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="d1f16-122">**En el nuevo servidor secundario**</span><span class="sxs-lookup"><span data-stu-id="d1f16-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="d1f16-123">Ejecute las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1f16-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="d1f16-124">Intercambiar roles</span><span class="sxs-lookup"><span data-stu-id="d1f16-124">Swapping Roles</span></span>  
 <span data-ttu-id="d1f16-125">Una vez realizados los pasos anteriores para realizar el cambio inicial de roles, ya puede cambiar los roles entre la base de datos principal y la secundaria. A tal efecto, siga los pasos descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="d1f16-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="d1f16-126">Para realizar el cambio de un rol, realice estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="d1f16-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="d1f16-127">Conecte en línea la base de datos secundaria y realice una copia de seguridad del registro de transacciones en el servidor principal mediante NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d1f16-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="d1f16-128">Deshabilite el trabajo de copia de seguridad de trasvase de registros en el servidor principal, así como los trabajos de copia y restauración en el servidor secundario original.</span><span class="sxs-lookup"><span data-stu-id="d1f16-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d1f16-129">Habilite el trabajo de copia de seguridad de trasvase de registros en el servidor secundario (el nuevo servidor principal), así como los trabajos de copia y restauración en el servidor primario (el nuevo servidor secundario).</span><span class="sxs-lookup"><span data-stu-id="d1f16-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1f16-130">Al cambiar una base de datos secundaria a la base de datos principal, para proporcionar una experiencia coherente a los usuarios y las aplicaciones, puede que tenga que volver a crear algunos o todos los metadatos de la base de datos; por ejemplo los inicios de sesión y los trabajos, en la nueva instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="d1f16-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="d1f16-131">Para obtener más información, vea [Administrar los metadatos cuando una base de datos pasa a estar disponible en otra instancia del servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1f16-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d1f16-132">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d1f16-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d1f16-133">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f16-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="d1f16-134">Administración de inicios de sesión y trabajos tras la conmutación de roles &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f16-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1f16-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1f16-135">See Also</span></span>  
 [<span data-ttu-id="d1f16-136">Tablas y procedimientos almacenados de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="d1f16-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
