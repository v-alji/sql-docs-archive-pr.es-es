---
title: Establecer la opción de configuración del servidor Tiempo de espera de consulta remota | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749473"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="119be-102">Establecer la opción de configuración del servidor Tiempo de espera de consulta remota</span><span class="sxs-lookup"><span data-stu-id="119be-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="119be-103">En este tema se describe cómo establecer la opción de configuración del servidor **tiempo de espera de consultas remotas** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119be-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="119be-104">La opción de **tiempo de espera de consultas remotas** especifica cuánto tiempo, en segundos, puede tardar una operación remota antes de que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supere el tiempo de espera. El valor predeterminado de esta opción es 600, lo que permite una espera de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="119be-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="119be-105">Este valor se aplica a una conexión saliente iniciada por el [!INCLUDE[ssDE](../../includes/ssde-md.md)] como una consulta remota.</span><span class="sxs-lookup"><span data-stu-id="119be-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="119be-106">Este valor no afecta a las consultas recibidas por el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119be-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="119be-107">Para deshabilitar el tiempo de espera, establezca el valor en 0.</span><span class="sxs-lookup"><span data-stu-id="119be-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="119be-108">Una consulta esperará hasta que finalice.</span><span class="sxs-lookup"><span data-stu-id="119be-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="119be-109">En el caso de las consultas heterogéneas, la opción de **tiempo de espera de consultas remotas** especifica los segundos (inicializados en el objeto de comando mediante la propiedad de conjunto de filas DBPROP_COMMANDTIMEOUT) que un proveedor remoto debe esperar a los conjuntos de resultados antes de que se agote el tiempo de espera de la consulta. Este valor se utiliza también para establecer DBPROP_GENERALTIMEOUT, si el proveedor remoto lo admite.</span><span class="sxs-lookup"><span data-stu-id="119be-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="119be-110">Esto hará que se agote el tiempo de espera de todas las demás operaciones después del número de segundos especificado.</span><span class="sxs-lookup"><span data-stu-id="119be-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="119be-111">Para los procedimientos almacenados remotos, la opción de **tiempo de espera de consultas remotas** especifica los segundos que deben transcurrir después de enviar una instrucción `EXEC` remota antes de que se agote el tiempo de espera del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="119be-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="119be-112">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="119be-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="119be-113">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="119be-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="119be-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="119be-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="119be-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="119be-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="119be-116">**Para configurar la opción de tiempo de espera de consultas remotas, use:**</span><span class="sxs-lookup"><span data-stu-id="119be-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="119be-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="119be-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="119be-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="119be-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="119be-119">**Seguimiento:**  [Después de configurar la opción de tiempo de espera de consultas remotas](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="119be-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="119be-120">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="119be-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="119be-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="119be-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="119be-122">Deben permitirse conexiones de servidor remoto para poder establecer este valor.</span><span class="sxs-lookup"><span data-stu-id="119be-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="119be-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="119be-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="119be-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="119be-124">Permissions</span></span>  
 <span data-ttu-id="119be-125">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="119be-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="119be-126">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="119be-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="119be-127">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="119be-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="119be-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="119be-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="119be-129">Para configurar la opción de tiempo de espera de consultas remotas</span><span class="sxs-lookup"><span data-stu-id="119be-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="119be-130">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="119be-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="119be-131">Haga clic en el nodo **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="119be-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="119be-132">En **Conexiones a servidores remotos**, en el cuadro **Tiempo de espera de consultas remotas** , escriba o seleccione un valor entre 0 y 2.147.483.647 para establecer el tiempo máximo de espera en segundos para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="119be-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="119be-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="119be-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="119be-134">Para configurar la opción de tiempo de espera de consultas remotas</span><span class="sxs-lookup"><span data-stu-id="119be-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="119be-135">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119be-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="119be-136">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="119be-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="119be-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="119be-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="119be-138">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `remote query timeout` en `0` , que deshabilita el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="119be-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="119be-139">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="119be-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="119be-140">Seguimiento: Después de configurar la opción de tiempo de espera de consultas remotas</span><span class="sxs-lookup"><span data-stu-id="119be-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="119be-141">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="119be-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119be-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="119be-142">See Also</span></span>  
 <span data-ttu-id="119be-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="119be-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="119be-144">[Propiedades y comportamientos de conjuntos de filas](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="119be-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="119be-145">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="119be-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="119be-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="119be-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
