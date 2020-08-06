---
title: Configurar la compresión de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677712"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="ca33f-102">Configurar la compresión de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ca33f-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="ca33f-103">En la instalación, la compresión de la copia de seguridad está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ca33f-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="ca33f-104">El comportamiento predeterminado para la compresión de la copia de seguridad lo define la opción de configuración de nivel de servidor **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="ca33f-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="ca33f-105">No obstante, puede invalidar el valor predeterminado de nivel de servidor al crear una copia de seguridad única o programar una serie de copias de seguridad rutinarias.</span><span class="sxs-lookup"><span data-stu-id="ca33f-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="ca33f-106">Para cambiar el valor predeterminado de nivel de servidor, vea [Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ca33f-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="ca33f-107">Invalidar el valor predeterminado de compresión de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ca33f-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="ca33f-108">Puede cambiar el comportamiento de la compresión de copia de seguridad para una copia de seguridad individual, trabajo de copia de seguridad o configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="ca33f-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="ca33f-109">Para invalidar el valor predeterminado de compresión de copia de seguridad de servidor al crear una copia de seguridad, use WITH NO_COMPRESSION o WITH COMPRESSION en la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ca33f-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="ca33f-110">En una configuración de trasvase de registros, puede controlar el comportamiento de la compresión de copia de seguridad de las copias de seguridad de registros mediante [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ca33f-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="ca33f-111">Para obtener más información sobre cómo ver o configurar la opción predeterminada de compresión de copia de seguridad de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ca33f-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="ca33f-112">Puede invalidar el valor predeterminado de la compresión de copia de seguridad de servidor al crear una copia de seguridad si especifica **Comprimir copia de seguridad** o **No comprimir copia de seguridad** en cualquiera de los cuadros de diálogo siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca33f-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="ca33f-113">Copia de seguridad de base de datos (página Opciones)</span><span class="sxs-lookup"><span data-stu-id="ca33f-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="ca33f-114">Al hacer una copia de seguridad de una base de datos, puede controlar la compresión de copia de seguridad de una base de datos, archivo o registro.</span><span class="sxs-lookup"><span data-stu-id="ca33f-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="ca33f-115">Usar el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="ca33f-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="ca33f-116">El Asistente para planes de mantenimiento le permite controlar la compresión de la copia de seguridad para cada copia de seguridad completa o diferencial de la base de datos o de registros programada.</span><span class="sxs-lookup"><span data-stu-id="ca33f-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="ca33f-117">[Tarea Copia de seguridad de la base de datos](../../integration-services/control-flow/back-up-database-task.md)de Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca33f-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="ca33f-118">Puede controlar el comportamiento de la compresión de copia de seguridad al crear un paquete para hacer un copia de seguridad de una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ca33f-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="ca33f-119">Configuración de copias de seguridad de trasvase de registros de transacciones</span><span class="sxs-lookup"><span data-stu-id="ca33f-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="ca33f-120">Puede controlar el comportamiento de compresión de las copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="ca33f-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="ca33f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca33f-121">See Also</span></span>  
 [<span data-ttu-id="ca33f-122">Compresión de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca33f-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
