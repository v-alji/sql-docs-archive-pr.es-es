---
title: Configurar la opción de configuración del servidor Límite de costo de regulador de consultas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663704"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="5e241-102">Configurar la opción de configuración del servidor Límite de costo de regulador de consultas</span><span class="sxs-lookup"><span data-stu-id="5e241-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="5e241-103">En este tema se describe cómo configurar la `query governor cost limit` opción de configuración del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e241-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5e241-104">La opción de límite de costo de regulador de consultas especifica un límite superior al periodo de tiempo en que una consulta puede ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="5e241-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="5e241-105">El costo de consulta hace referencia al tiempo estimado, en segundos, que se necesita para completar una consulta con una configuración de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="5e241-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="5e241-106">El valor predeterminado de esta opción es 0, que establece el regulador de consultas en OFF.</span><span class="sxs-lookup"><span data-stu-id="5e241-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="5e241-107">Esto permite que todas las consultas se ejecuten sin limitación de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5e241-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="5e241-108">Si especifica un valor positivo distinto de cero, el regulador de consultas no permitirá la ejecución de ninguna consulta que tenga un costo estimado superior a ese valor.</span><span class="sxs-lookup"><span data-stu-id="5e241-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="5e241-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5e241-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e241-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5e241-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e241-111">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5e241-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5e241-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5e241-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e241-113">**Para configurar la opción de límite de costo de regulador de consultas, use:**</span><span class="sxs-lookup"><span data-stu-id="5e241-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="5e241-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e241-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e241-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e241-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5e241-116">**Seguimiento:**  [Después de configurar la opción de límite de costo de regulador de consultas](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5e241-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e241-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5e241-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5e241-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="5e241-118">Recommendations</span></span>  
  
-   <span data-ttu-id="5e241-119">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="5e241-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5e241-120">Para cambiar el valor de límite de costo de regulador de consultas en cada conexión, use la instrucción [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5e241-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e241-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5e241-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e241-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="5e241-122">Permissions</span></span>  
 <span data-ttu-id="5e241-123">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="5e241-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5e241-124">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5e241-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5e241-125">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="5e241-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e241-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e241-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="5e241-127">Para configurar la opción de límite de costo de regulador de consultas</span><span class="sxs-lookup"><span data-stu-id="5e241-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="5e241-128">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e241-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5e241-129">Haga clic en la página **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="5e241-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="5e241-130">Active o desactive la casilla **Usar el regulador de consultas para evitar consultas que se ejecuten durante mucho tiempo** .</span><span class="sxs-lookup"><span data-stu-id="5e241-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="5e241-131">Si activa esta casilla, en el cuadro inferior, escriba un valor positivo, que utiliza el regulador de consultas para no permitir la ejecución de ninguna consulta con una duración de ejecución que supere ese valor.</span><span class="sxs-lookup"><span data-stu-id="5e241-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e241-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e241-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="5e241-133">Para configurar la opción de límite de costo de regulador de consultas</span><span class="sxs-lookup"><span data-stu-id="5e241-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="5e241-134">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e241-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e241-135">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5e241-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e241-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5e241-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5e241-137">Este ejemplo muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción `query governor cost limit` en `120` segundos.</span><span class="sxs-lookup"><span data-stu-id="5e241-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="5e241-138">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5e241-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a> <span data-ttu-id="5e241-139">Seguimiento: Después de configurar la opción de límite de costo de regulador de consultas</span><span class="sxs-lookup"><span data-stu-id="5e241-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="5e241-140">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5e241-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e241-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e241-141">See Also</span></span>  
 <span data-ttu-id="5e241-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e241-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5e241-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e241-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="5e241-144">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5e241-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5e241-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5e241-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
