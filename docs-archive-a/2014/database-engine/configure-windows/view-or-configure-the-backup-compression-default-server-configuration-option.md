---
title: Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677869"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="eb524-102">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="eb524-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="eb524-103">En este tema se describe cómo ver o configurar la opción de configuración del servidor **Compresión de copia de seguridad predeterminada** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb524-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="eb524-104">La opción **Compresión de copia de seguridad predeterminada** determina si la instancia de servidor crea copias de seguridad comprimidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb524-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="eb524-105">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado, la opción **Compresión de copia de seguridad predeterminada** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="eb524-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="eb524-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="eb524-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eb524-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="eb524-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eb524-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="eb524-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="eb524-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="eb524-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="eb524-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="eb524-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eb524-111">**Para ver o configurar la opción de valor predeterminado de compresión de copia de seguridad, use:**</span><span class="sxs-lookup"><span data-stu-id="eb524-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="eb524-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb524-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eb524-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb524-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="eb524-114">**Seguimiento:**  [Después de configurar la opción de valor predeterminado de compresión de copia de seguridad](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="eb524-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eb524-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="eb524-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="eb524-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="eb524-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="eb524-117">La compresión no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb524-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eb524-118">Para obtener más información, vea [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="eb524-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="eb524-119">De forma predeterminada, la compresión aumenta significativamente el uso de CPU y la CPU adicional que consume el proceso de compresión puede afectar adversamente a las operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="eb524-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="eb524-120">Por consiguiente, podría ser conveniente crear copias de seguridad comprimidas de prioridad baja en una sesión en la que el [regulador de recursos](../../relational-databases/resource-governor/resource-governor.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="eb524-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="eb524-121">Para obtener más información, vea [Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="eb524-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="eb524-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="eb524-122">Recommendations</span></span>  
  
-   <span data-ttu-id="eb524-123">Al crear una copia de seguridad individual, establecer una configuración de trasvase de registros o crear un plan de mantenimiento, puede invalidar el valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb524-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="eb524-124">La compresión de copia de seguridad se admite para dispositivos de copia de seguridad en disco y en cinta.</span><span class="sxs-lookup"><span data-stu-id="eb524-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eb524-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="eb524-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eb524-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="eb524-126">Permissions</span></span>  
 <span data-ttu-id="eb524-127">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="eb524-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="eb524-128">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="eb524-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="eb524-129">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="eb524-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eb524-130">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb524-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="eb524-131">Para ver o configurar la opción de valor predeterminado de compresión de copia</span><span class="sxs-lookup"><span data-stu-id="eb524-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="eb524-132">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eb524-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="eb524-133">Haga clic en el nodo **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="eb524-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="eb524-134">En **Copias de seguridad y restauración**, **Comprimir copia de seguridad** muestra el valor actual de la opción **Compresión de copia de seguridad predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="eb524-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="eb524-135">Esta opción determina el valor predeterminado de nivel de servidor para comprimir copias de seguridad, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="eb524-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="eb524-136">Si la casilla **Comprimir copia de seguridad** se deja en blanco, las nuevas copias de seguridad no se comprimirán de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb524-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="eb524-137">Si la casilla **Comprimir copia de seguridad** se activa, las nuevas copias de seguridad se comprimirán de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb524-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="eb524-138">Si es miembro de los roles fijos de servidor **sysadmin** o **serveradmin** , puede cambiar también el valor predeterminado haciendo clic en la casilla **Comprimir copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="eb524-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eb524-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb524-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="eb524-140">Para ver la opción de valor predeterminado de compresión de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="eb524-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="eb524-141">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb524-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb524-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="eb524-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eb524-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="eb524-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="eb524-144">En este ejemplo se consulta la vista de catálogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) para determinar el valor de `backup compression default`.</span><span class="sxs-lookup"><span data-stu-id="eb524-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="eb524-145">El valor 0 significa que la compresión de copia de seguridad está desactivada y el valor 1 significa que la compresión está habilitada.</span><span class="sxs-lookup"><span data-stu-id="eb524-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="eb524-146">Para configurar la opción de valor predeterminado de compresión de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="eb524-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="eb524-147">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb524-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb524-148">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="eb524-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eb524-149">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="eb524-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="eb524-150">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar la instancia de servidor con el fin de crear copias de seguridad comprimidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eb524-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="eb524-151">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb524-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a> <span data-ttu-id="eb524-152">Seguimiento: Después de configurar la opción de valor predeterminado de compresión de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="eb524-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="eb524-153">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="eb524-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb524-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb524-154">See Also</span></span>  
 <span data-ttu-id="eb524-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb524-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="eb524-156">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb524-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="eb524-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb524-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="eb524-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb524-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="eb524-159">Información general de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb524-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
