---
title: Ver o cambiar las propiedades del servidor (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744853"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="3cbbc-102">Ver o cambiar las propiedades del servidor (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3cbbc-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="3cbbc-103">En este tema se describe cómo ver o cambiar las propiedades de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="3cbbc-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="3cbbc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3cbbc-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="3cbbc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3cbbc-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3cbbc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3cbbc-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3cbbc-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3cbbc-108">**Para ver o cambiar las propiedades del servidor, usando:**</span><span class="sxs-lookup"><span data-stu-id="3cbbc-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="3cbbc-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cbbc-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3cbbc-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbbc-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3cbbc-111">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3cbbc-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="3cbbc-112">**Seguimiento:**  [después de cambiar propiedades del servidor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3cbbc-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3cbbc-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3cbbc-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3cbbc-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3cbbc-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3cbbc-115">Cuando utilice sp_configure, deberá ejecutar RECONFIGURE o RECONFIGURE WITH OVERRIDE después de establecer una opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="3cbbc-116">La instrucción RECONFIGURE WITH OVERRIDE se suele reservar para opciones de configuración que deberían utilizarse con extrema precaución.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="3cbbc-117">No obstante, RECONFIGURE WITH OVERRIDE funciona con todas las opciones de configuración y puede utilizarlo en lugar de RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cbbc-118">RECONFIGURE se ejecuta en una transacción.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="3cbbc-119">Si una de las operaciones de reconfiguración genera un error, ninguna de estas operaciones surtirá efecto.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="3cbbc-120">Algunas páginas de propiedades presentan información obtenida mediante Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="3cbbc-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="3cbbc-121">Para mostrar dichas páginas, WMI debe estar instalado en el equipo en el que se ejecuta [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbbc-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3cbbc-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3cbbc-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3cbbc-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="3cbbc-123">Permissions</span></span>  
 <span data-ttu-id="3cbbc-124">Para obtener más información, vea [Roles de nivel de servidor](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3cbbc-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="3cbbc-125">De `sp_configure` forma predeterminada, los permisos de ejecución en sin parámetros o con solo el primer parámetro se conceden a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="3cbbc-126">Para ejecutar `sp_configure` con ambos parámetros para cambiar una opción de configuración o ejecutar la instrucción REconfigure, se debe conceder al usuario el permiso de nivel de servidor Alter Settings.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="3cbbc-127">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3cbbc-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cbbc-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="3cbbc-129">Para ver o cambiar las propiedades del servidor</span><span class="sxs-lookup"><span data-stu-id="3cbbc-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="3cbbc-130">En el Explorador de objetos, haga clic con el botón derecho en un servidor y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3cbbc-131">En el cuadro de diálogo **Propiedades del servidor** , haga clic en una página para ver o cambiar la información de servidor acerca de dicha página.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="3cbbc-132">Algunas propiedades son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3cbbc-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbbc-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="3cbbc-134">Para ver las propiedades del servidor mediante la función integrada SERVERPROPERTY</span><span class="sxs-lookup"><span data-stu-id="3cbbc-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="3cbbc-135">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbbc-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cbbc-136">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cbbc-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3cbbc-138">En este ejemplo se emplea la función integrada [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) en una instrucción `SELECT` para devolver información sobre el servidor actual.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="3cbbc-139">Este escenario es útil cuando hay varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en un servidor basado en Windows y el cliente debe abrir otra conexión a la misma instancia usada por la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="3cbbc-140">Para ver las propiedades del servidor mediante la vista de catálogo sys.servers</span><span class="sxs-lookup"><span data-stu-id="3cbbc-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="3cbbc-141">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbbc-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cbbc-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cbbc-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3cbbc-144">En este ejemplo se consulta la vista de catálogo [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) para devolver el nombre (`name`) y el identificador (`server_id`) del servidor actual, además del nombre del proveedor OLE DB (`provider`) para conectarse a un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="3cbbc-145">Para ver las propiedades del servidor mediante la vista de catálogo sys.configurations</span><span class="sxs-lookup"><span data-stu-id="3cbbc-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="3cbbc-146">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbbc-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cbbc-147">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cbbc-148">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3cbbc-149">En este ejemplo se consulta la vista de catálogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) para devolver información sobre cada opción de configuración del servidor actual.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="3cbbc-150">El ejemplo devuelve el nombre (`name`) y la descripción (`description`) de la opción y si se trata de una opción avanzada (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="3cbbc-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="3cbbc-151">Para cambiar una propiedad del servidor mediante sp_configure</span><span class="sxs-lookup"><span data-stu-id="3cbbc-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="3cbbc-152">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbbc-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cbbc-153">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cbbc-154">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3cbbc-155">Este ejemplo muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para cambiar una propiedad del servidor.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="3cbbc-156">El ejemplo cambia el valor de la opción `fill factor` a `100`.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="3cbbc-157">El servidor debe reiniciarse para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="3cbbc-158">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cbbc-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3cbbc-159">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3cbbc-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="3cbbc-160">Algunas propiedades del servidor se pueden ver o cambiar mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="3cbbc-161">Por ejemplo, puede ver la versión y la edición de la instancia de SQL Server, o cambiar la ubicación donde se almacenan los archivos de registro de errores.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="3cbbc-162">Estas propiedades también se pueden ver si se consultan las [Funciones y vistas de administración dinámica relacionadas con servidores](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cbbc-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="3cbbc-163">Para ver o cambiar las propiedades del servidor</span><span class="sxs-lookup"><span data-stu-id="3cbbc-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="3cbbc-164">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="3cbbc-165">En **Administrador de configuración de SQL Server**, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="3cbbc-166">En el panel de detalles, haga clic con el botón derecho en **SQL Server (\<***instancename***>)** y, después, en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3cbbc-167">En el cuadro de diálogo **Propiedades de SQL Server (\<***instancename***>)** , cambie las propiedades en la pestaña **Servicio** o **Avanzado** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a><span data-ttu-id="3cbbc-168">Seguimiento: después de cambiar las propiedades del servidor</span><span class="sxs-lookup"><span data-stu-id="3cbbc-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="3cbbc-169">Para algunas propiedades, puede que sea necesario reiniciar el servidor para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="3cbbc-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbbc-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cbbc-170">See Also</span></span>  
 <span data-ttu-id="3cbbc-171">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="3cbbc-172">[Instrucciones SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="3cbbc-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="3cbbc-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="3cbbc-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="3cbbc-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="3cbbc-177">[Configurar WMI para mostrar el estado del servidor en Herramientas de SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="3cbbc-178">[Administrador de configuración de SQL Server](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="3cbbc-179">[Funciones de configuración &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbbc-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="3cbbc-180">Funciones y vistas de administración dinámica relacionadas con servidores &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbbc-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
