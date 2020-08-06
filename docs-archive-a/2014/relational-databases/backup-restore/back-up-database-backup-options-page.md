---
title: Realizar copias de seguridad de la base de datos (página Opciones de copia de seguridad) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677728"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="42120-102">Copia de seguridad de la base de datos (página Opciones de copia de seguridad)</span><span class="sxs-lookup"><span data-stu-id="42120-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="42120-103">Utilice la página  **Opciones de copia de seguridad** del cuadro de diálogo **Copia de seguridad de base de datos** para ver o modificar las opciones de copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="42120-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="42120-104">**Para crear una copia de seguridad mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="42120-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="42120-105">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42120-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="42120-106">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42120-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42120-107">Puede definir un plan de mantenimiento de base de datos para crear copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="42120-108">Para obtener más información, vea [Planes de mantenimiento](../maintenance-plans/maintenance-plans.md) y [Usar el Asistente para planes de mantenimiento](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="42120-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42120-109">Cuando especifica una tarea de copia de seguridad con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puede generar el script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span><span class="sxs-lookup"><span data-stu-id="42120-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42120-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="42120-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="42120-111">Conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="42120-111">Backup set</span></span>  
 <span data-ttu-id="42120-112">Las opciones del panel **Conjunto de copia de seguridad** permiten especificar información adicional acerca del conjunto de copia de seguridad creado en la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="42120-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="42120-113">**Name**</span></span>  
 <span data-ttu-id="42120-114">Especifique el nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-114">Specify the backup set name.</span></span> <span data-ttu-id="42120-115">El sistema sugiere automáticamente un nombre predeterminado basándose en el nombre de la base de datos y el tipo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="42120-116">Para obtener más información sobre los conjuntos de copia de seguridad, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42120-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="42120-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="42120-117">**Description**</span></span>  
 <span data-ttu-id="42120-118">Escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="42120-119">**El conjunto de copia de seguridad expira**</span><span class="sxs-lookup"><span data-stu-id="42120-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="42120-120">Elija una de las siguientes opciones de expiración.</span><span class="sxs-lookup"><span data-stu-id="42120-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="42120-121">Esta opción se deshabilita si la opción **Dirección URL** se elige como destino de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42120-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42120-122">**Después**</span><span class="sxs-lookup"><span data-stu-id="42120-122">**After**</span></span>|<span data-ttu-id="42120-123">Especifique el número de días que debe transcurrir antes de que el conjunto de copia de seguridad expire y se pueda sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="42120-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="42120-124">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="42120-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="42120-125">El valor predeterminado para la expiración de la copia de seguridad es el valor configurado en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** .</span><span class="sxs-lookup"><span data-stu-id="42120-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="42120-126">Para tener acceso a esta opción, haga clic con el botón derecho en el nombre del servidor en el Explorador de objetos y seleccione **Propiedades**; luego, haga clic en la página **Configuración de base de datos** del cuadro de diálogo **Propiedades del servidor** .</span><span class="sxs-lookup"><span data-stu-id="42120-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="42120-127">**Activado**</span><span class="sxs-lookup"><span data-stu-id="42120-127">**On**</span></span>|<span data-ttu-id="42120-128">Especifique una fecha determinada en la que el conjunto de copias de seguridad expire y se pueda sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="42120-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="42120-129">Compresión</span><span class="sxs-lookup"><span data-stu-id="42120-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="42120-130">(o las versiones posteriores) admiten la [compresión de copia de seguridad](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42120-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="42120-131">**Establecer la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="42120-131">**Set backup compression**</span></span>  
 <span data-ttu-id="42120-132">En [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (o en versiones posteriores), seleccione uno de los siguientes valores de compresión de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="42120-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42120-133">**Usar la configuración de servidor predeterminada**</span><span class="sxs-lookup"><span data-stu-id="42120-133">**Use the default server setting**</span></span>|<span data-ttu-id="42120-134">Haga clic para utilizar el valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="42120-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="42120-135">La opción de la configuración del servidor **Compresión de copia de seguridad predeterminada** establece este valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="42120-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="42120-136">Para obtener más información sobre cómo ver la configuración actual de esta opción, vea [Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="42120-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="42120-137">**Comprimir copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="42120-137">**Compress backup**</span></span>|<span data-ttu-id="42120-138">Haga clic para comprimir la copia de seguridad, sin tener en cuenta el valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="42120-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="42120-139">**\*\* Importante \*\*** De forma predeterminada, la compresión aumenta significativamente el uso de CPU y la CPU adicional que consume el proceso de compresión puede afectar negativamente a las operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="42120-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="42120-140">Por consiguiente, podría ser conveniente crear copias de seguridad comprimidas de prioridad baja en una sesión en la que el [regulador de recursos](../resource-governor/resource-governor.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="42120-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="42120-141">Para obtener más información, vea [Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="42120-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="42120-142">**No comprimir copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="42120-142">**Do not compress backup**</span></span>|<span data-ttu-id="42120-143">Haga clic para crear una copia de seguridad sin comprimir, independientemente del valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="42120-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="42120-144">Cifrado</span><span class="sxs-lookup"><span data-stu-id="42120-144">Encryption</span></span>  
 <span data-ttu-id="42120-145">Para crear un archivo de copia de seguridad, active la casilla **Cifrar copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="42120-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="42120-146">Seleccione un algoritmo de cifrado para usar para el paso de cifrado y proporcione un certificado o clave asimétrica de una lista de los certificados existentes o de claves asimétricas.</span><span class="sxs-lookup"><span data-stu-id="42120-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="42120-147">Los algoritmos disponibles para el cifrado son:</span><span class="sxs-lookup"><span data-stu-id="42120-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="42120-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="42120-148">AES 128</span></span>  
  
-   <span data-ttu-id="42120-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="42120-149">AES 192</span></span>  
  
-   <span data-ttu-id="42120-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="42120-150">AES 256</span></span>  
  
-   <span data-ttu-id="42120-151">Triple DES</span><span class="sxs-lookup"><span data-stu-id="42120-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="42120-152">La opción de cifrado se deshabilita si seleccionó anexar en un conjunto de copia de seguridad existente.</span><span class="sxs-lookup"><span data-stu-id="42120-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="42120-153">Es una práctica recomendada hacer copias de seguridad del certificado o las claves y almacenarlas en una ubicación diferente que la copia de seguridad que cifró.</span><span class="sxs-lookup"><span data-stu-id="42120-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="42120-154">Solo se admiten las claves que residen en Administración extensible de claves (EKM).</span><span class="sxs-lookup"><span data-stu-id="42120-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42120-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42120-155">See Also</span></span>  
 <span data-ttu-id="42120-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42120-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="42120-157">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42120-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="42120-158">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42120-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="42120-159">Realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42120-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
