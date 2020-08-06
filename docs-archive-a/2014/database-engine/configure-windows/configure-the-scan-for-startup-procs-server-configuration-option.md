---
title: Establecer la opción de configuración del servidor Buscar procedimientos de inicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671162"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="084d9-102">Establecer la opción de configuración del servidor Buscar procedimientos de inicio</span><span class="sxs-lookup"><span data-stu-id="084d9-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="084d9-103">En este tema se describe cómo establecer la opción de configuración del servidor **buscar procedimientos de inicio** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="084d9-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="084d9-104">Use la opción de **buscar procedimientos de inicio** para buscar la ejecución automática de procedimientos almacenados durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="084d9-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="084d9-105">Si el valor de esta opción se establece en 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buscará y ejecutará todos los procedimientos almacenados de ejecución automática definidos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="084d9-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="084d9-106">El valor predeterminado de **Buscar procedimientos de inicio** es 0 (no buscar).</span><span class="sxs-lookup"><span data-stu-id="084d9-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="084d9-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="084d9-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="084d9-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="084d9-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="084d9-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="084d9-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="084d9-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="084d9-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="084d9-111">**Para configurar la opción de buscar procedimientos de inicio, use:**</span><span class="sxs-lookup"><span data-stu-id="084d9-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="084d9-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="084d9-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="084d9-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="084d9-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="084d9-114">**Seguimiento:**  [Después de configurar la opción de buscar procedimientos de inicio](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="084d9-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="084d9-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="084d9-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="084d9-116">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="084d9-116">Recommendations</span></span>  
  
-   <span data-ttu-id="084d9-117">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="084d9-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="084d9-118">El valor de esta opción puede especificarse mediante **sp_configure**. Pero se establecerá automáticamente si usa **sp_procoption**, que marca o desmarca los procedimientos almacenados de ejecución automática.</span><span class="sxs-lookup"><span data-stu-id="084d9-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="084d9-119">Cuando se usa **sp_procoption** para marcar el primer procedimiento almacenado como procedimiento automático, esta opción se establece automáticamente en el valor 1.</span><span class="sxs-lookup"><span data-stu-id="084d9-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="084d9-120">Cuando se usa **sp_procoption** para desmarcar el último procedimiento almacenado como procedimiento automático, esta opción se establece automáticamente en el valor 0.</span><span class="sxs-lookup"><span data-stu-id="084d9-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="084d9-121">Si usa **sp_procoption** para marcar y desmarcar los procedimientos automáticos, y si siempre los desmarca antes de quitarlos, no hay necesidad de establecer esta opción manualmente.</span><span class="sxs-lookup"><span data-stu-id="084d9-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="084d9-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="084d9-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="084d9-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="084d9-123">Permissions</span></span>  
 <span data-ttu-id="084d9-124">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="084d9-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="084d9-125">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="084d9-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="084d9-126">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="084d9-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="084d9-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="084d9-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="084d9-128">Para configurar la opción scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="084d9-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="084d9-129">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="084d9-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="084d9-130">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="084d9-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="084d9-131">En **Varios**, cambie la opción **Buscar procedimientos de inicio** a True o False seleccionando el valor que quiera en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="084d9-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="084d9-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="084d9-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="084d9-133">Para configurar la opción scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="084d9-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="084d9-134">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="084d9-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="084d9-135">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="084d9-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="084d9-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="084d9-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="084d9-137">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `scan for startup procs` en `1`.</span><span class="sxs-lookup"><span data-stu-id="084d9-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> <span data-ttu-id="084d9-138">Seguimiento: Después de configurar la opción de buscar procedimientos de inicio</span><span class="sxs-lookup"><span data-stu-id="084d9-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="084d9-139">El servidor debe reiniciarse para que el valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="084d9-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084d9-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="084d9-140">See Also</span></span>  
 <span data-ttu-id="084d9-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="084d9-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="084d9-142">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="084d9-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="084d9-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="084d9-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="084d9-144">sp_procoption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="084d9-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
