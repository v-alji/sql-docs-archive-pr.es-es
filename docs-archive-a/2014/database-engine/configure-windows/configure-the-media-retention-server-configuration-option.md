---
title: Establecer la opción de configuración del servidor Retención de medios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671171"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="f03a3-102">Establecer la opción de configuración del servidor Retención de medios</span><span class="sxs-lookup"><span data-stu-id="f03a3-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="f03a3-103">En este tema se describe cómo establecer la opción de configuración del servidor **retención de medios** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f03a3-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f03a3-104">La opción de **retención de medios** especifica el tiempo que se conserva cada conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f03a3-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="f03a3-105">La opción ayuda a proteger las copias de seguridad para que no puedan sobrescribirse hasta que haya transcurrido el número de días especificado.</span><span class="sxs-lookup"><span data-stu-id="f03a3-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="f03a3-106">Después de configurar la opción de **retención de medios** , no necesitará especificar el intervalo de tiempo que se van a conservar las copias de seguridad del sistema cada vez que realice una.</span><span class="sxs-lookup"><span data-stu-id="f03a3-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="f03a3-107">El valor predeterminado es 0 días y el valor máximo es 365 días.</span><span class="sxs-lookup"><span data-stu-id="f03a3-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="f03a3-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f03a3-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f03a3-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f03a3-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f03a3-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f03a3-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f03a3-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f03a3-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f03a3-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f03a3-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f03a3-113">**Para configurar la opción de retención de medios, use:**</span><span class="sxs-lookup"><span data-stu-id="f03a3-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="f03a3-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f03a3-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f03a3-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f03a3-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f03a3-116">**Seguimiento:**  [Después de configurar la opción de retención de medios](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f03a3-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f03a3-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f03a3-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f03a3-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f03a3-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f03a3-119">Si usa el medio de copia de seguridad antes de que haya transcurrido el número de días especificado, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emitirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="f03a3-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f03a3-120">no emite un mensaje de advertencia a menos que se cambie el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f03a3-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f03a3-121">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f03a3-121">Recommendations</span></span>  
  
-   <span data-ttu-id="f03a3-122">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="f03a3-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="f03a3-123">La opción de **retención de medios** se puede invalidar mediante la cláusula RETAINDAYS de la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f03a3-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f03a3-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f03a3-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f03a3-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="f03a3-125">Permissions</span></span>  
 <span data-ttu-id="f03a3-126">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="f03a3-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f03a3-127">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f03a3-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f03a3-128">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="f03a3-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f03a3-129">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f03a3-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="f03a3-130">Para configurar la opción de retención de medios</span><span class="sxs-lookup"><span data-stu-id="f03a3-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="f03a3-131">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f03a3-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f03a3-132">Haga clic en el nodo **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="f03a3-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="f03a3-133">En **Copia de seguridad o restauración**, en el cuadro **Tiempo predeterminado de retención de medios de copia de seguridad** , escriba o seleccione un valor entre 0 y 365 para establecer el número de días que se conservará el medio de copia de seguridad, tras realizar la copia de seguridad de una base de datos o del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="f03a3-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f03a3-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f03a3-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="f03a3-135">Para configurar la opción de retención de medios</span><span class="sxs-lookup"><span data-stu-id="f03a3-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="f03a3-136">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f03a3-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f03a3-137">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f03a3-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f03a3-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f03a3-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f03a3-139">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `media retention` en `60` días.</span><span class="sxs-lookup"><span data-stu-id="f03a3-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="f03a3-140">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f03a3-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a> <span data-ttu-id="f03a3-141">Seguimiento: Después de configurar la opción de retención de medios</span><span class="sxs-lookup"><span data-stu-id="f03a3-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="f03a3-142">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="f03a3-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03a3-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f03a3-143">See Also</span></span>  
 <span data-ttu-id="f03a3-144">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f03a3-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="f03a3-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03a3-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f03a3-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03a3-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f03a3-147">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f03a3-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="f03a3-148">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f03a3-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
