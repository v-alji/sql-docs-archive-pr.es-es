---
title: Establecer la opción de configuración del servidor Intervalo de recuperación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663703"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="4dc0c-102">Establecer la opción de configuración del servidor Intervalo de recuperación</span><span class="sxs-lookup"><span data-stu-id="4dc0c-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="4dc0c-103">En este tema se describe cómo establecer la opción de configuración del servidor **intervalo de recuperación** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc0c-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4dc0c-104">La opción de **intervalo de recuperación** define un límite superior para el tiempo que debe tardar la recuperación de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="4dc0c-105">El [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa el valor especificado en esta opción para determinar aproximadamente la frecuencia con la que deben emitirse los [puntos de comprobación automáticos](../../relational-databases/logs/database-checkpoints-sql-server.md) en una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="4dc0c-106">El valor de intervalo de recuperación predeterminado es 0, lo que permite que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] configure automáticamente el intervalo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="4dc0c-107">Normalmente, el intervalo de recuperación predeterminado tiene como resultado que los puntos de comprobación automáticos se produzcan aproximadamente cada minuto en las bases de datos activas con un tiempo de recuperación inferior a un minuto.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="4dc0c-108">Los valores más altos indican el tiempo de recuperación máximo aproximado, en minutos.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="4dc0c-109">Por ejemplo, si el intervalo de recuperación se establece en 3, indica un tiempo de recuperación máximo de aproximadamente tres minutos.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="4dc0c-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4dc0c-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4dc0c-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4dc0c-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4dc0c-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4dc0c-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4dc0c-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4dc0c-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4dc0c-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4dc0c-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4dc0c-115">**Para establecer la opción de configuración del servidor de intervalo de recuperación, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="4dc0c-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="4dc0c-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dc0c-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4dc0c-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dc0c-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4dc0c-118">**Seguimiento:**  [después de configurar la opción de intervalo de recuperación](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4dc0c-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4dc0c-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4dc0c-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4dc0c-120">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4dc0c-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4dc0c-121">El intervalo de recuperación afecta solo a las bases de datos que usan el tiempo de recuperación predeterminado de destino (0).</span><span class="sxs-lookup"><span data-stu-id="4dc0c-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="4dc0c-122">Para invalidar el intervalo de recuperación de servidor en una base de datos, configure un tiempo de recuperación de destino no predeterminado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="4dc0c-123">Para obtener más información, vea [Cambiar el tiempo de recuperación de destino de una base de datos &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dc0c-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4dc0c-124">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4dc0c-124">Recommendations</span></span>  
  
-   <span data-ttu-id="4dc0c-125">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="4dc0c-126">Normalmente, se recomienda mantener el intervalo de recuperación en 0, a menos que experimente problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="4dc0c-127">Si decide aumentar el valor de intervalo de recuperación, es recomendable que lo haga gradualmente en pequeños incrementos y que evalúe el efecto de cada aumento incremental en el rendimiento de la recuperación.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="4dc0c-128">Si usa **sp_configure** para cambiar el valor de la opción de **intervalo de recuperación** a más de 60 (minutos), especifique RECONFIGURE WITH OVERRIDE.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="4dc0c-129">WITH OVERRIDE deshabilita la comprobación de los valores de configuración (para los valores no válidos o que no se recomiendan).</span><span class="sxs-lookup"><span data-stu-id="4dc0c-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4dc0c-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4dc0c-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4dc0c-131">Permisos</span><span class="sxs-lookup"><span data-stu-id="4dc0c-131">Permissions</span></span>  
 <span data-ttu-id="4dc0c-132">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4dc0c-133">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4dc0c-134">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4dc0c-135">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dc0c-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4dc0c-136">**Para establecer el intervalo de recuperación**</span><span class="sxs-lookup"><span data-stu-id="4dc0c-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="4dc0c-137">En el Explorador de objetos, haga clic con el botón derecho en una instancia del servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4dc0c-138">Haga clic en el nodo **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="4dc0c-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="4dc0c-139">En **Recuperación**, en el cuadro **Intervalo de recuperación (min)** , escriba o seleccione un valor entre 0 y 32767 para establecer el tiempo máximo, en minutos, que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe emplear en recuperar cada base de datos cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="4dc0c-140">El valor predeterminado es 0, que indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]lo configura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4dc0c-141">En la práctica, esto significa un tiempo de recuperación inferior a un minuto y un punto de comprobación aproximadamente cada minuto para bases de datos activas.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4dc0c-142">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dc0c-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="4dc0c-143">Para establecer el intervalo de recuperación</span><span class="sxs-lookup"><span data-stu-id="4dc0c-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="4dc0c-144">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc0c-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4dc0c-145">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4dc0c-146">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4dc0c-147">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `recovery interval` en `3` minutos.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="4dc0c-148">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dc0c-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a> <span data-ttu-id="4dc0c-149">Seguimiento: después de configurar la opción de intervalo de recuperación</span><span class="sxs-lookup"><span data-stu-id="4dc0c-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="4dc0c-150">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="4dc0c-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc0c-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dc0c-151">See Also</span></span>  
 <span data-ttu-id="4dc0c-152">[Cambiar el tiempo de recuperación de destino de una base de datos &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dc0c-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="4dc0c-153">[Puntos de comprobación de base de datos &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dc0c-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="4dc0c-154">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dc0c-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="4dc0c-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dc0c-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="4dc0c-156">[Opción de configuración del servidor Mostrar opciones avanzadas](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4dc0c-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="4dc0c-157">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4dc0c-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
