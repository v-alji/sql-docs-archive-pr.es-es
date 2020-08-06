---
title: Establecer la opción de configuración del servidor Conexiones de usuario | Microsoft Docs
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663105"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="3a31f-102">Establecer la opción de configuración del servidor Conexiones de usuario</span><span class="sxs-lookup"><span data-stu-id="3a31f-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="3a31f-103">En este tema se describe cómo establecer la opción de configuración del servidor **conexiones de usuario** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a31f-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3a31f-104">La opción de **conexiones de usuario** especifica el número máximo de conexiones de usuario simultáneas que se permiten en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a31f-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3a31f-105">El número real de conexiones de usuario permitidas depende también de la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se use y de los límites de las aplicaciones y del hardware.</span><span class="sxs-lookup"><span data-stu-id="3a31f-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3a31f-106">permite un máximo de 32.767 conexiones de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a31f-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="3a31f-107">Como la opción **user connections** es una opción dinámica (autoconfiguración), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajusta automáticamente el número máximo de conexiones de usuario a medida que se necesitan, hasta el valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="3a31f-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="3a31f-108">Por ejemplo, si solo 10 usuarios han iniciado una sesión, se asignan 10 objetos de conexión de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a31f-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="3a31f-109">En la mayoría de los casos, no es necesario cambiar el valor de esta opción.</span><span class="sxs-lookup"><span data-stu-id="3a31f-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="3a31f-110">El valor predeterminado es 0, lo que significa que se permite un máximo de 32 767 conexiones de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a31f-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="3a31f-111">Para determinar el número máximo de conexiones de usuario que el sistema permite, puede ejecutar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) o consultar la vista de catálogo [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3a31f-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="3a31f-112">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="3a31f-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a31f-113">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="3a31f-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a31f-114">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3a31f-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="3a31f-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3a31f-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a31f-116">**Para configurar la opción de conexiones de usuario, use:**</span><span class="sxs-lookup"><span data-stu-id="3a31f-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="3a31f-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a31f-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3a31f-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a31f-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="3a31f-119">**Seguimiento:**  [Después de configurar la opción de conexiones de usuario](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3a31f-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a31f-120">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3a31f-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3a31f-121">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3a31f-121">Recommendations</span></span>  
  
-   <span data-ttu-id="3a31f-122">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="3a31f-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="3a31f-123">Usar la opción de **conexiones de usuario** ayuda a evitar que el servidor se sobrecargue con demasiadas conexiones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="3a31f-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="3a31f-124">Puede calcular el número de conexiones basándose en los requisitos del sistema y de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a31f-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="3a31f-125">Por ejemplo, en un sistema con muchos usuarios, cada usuario no necesitará normalmente una conexión exclusiva.</span><span class="sxs-lookup"><span data-stu-id="3a31f-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="3a31f-126">Los usuarios pueden compartir las conexiones.</span><span class="sxs-lookup"><span data-stu-id="3a31f-126">Connections can be shared among users.</span></span> <span data-ttu-id="3a31f-127">Los usuarios que ejecutan aplicaciones de OLE DB necesitan una conexión para cada objeto de conexión abierta, los que ejecutan aplicaciones de Conectividad abierta de bases de datos (ODBC) necesitan una conexión para cada controlador de conexión activo de la aplicación y los que ejecutan aplicaciones de DB-Library necesitan una conexión para cada proceso iniciado que llame a la función **dbopen** de DB-Library.</span><span class="sxs-lookup"><span data-stu-id="3a31f-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a31f-128">Si tiene que utilizar esta opción, no establezca un valor demasiado alto, ya que cada conexión tiene sobrecarga, independientemente de si la conexión se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="3a31f-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="3a31f-129">Si se supera el número máximo de conexiones de usuario, recibirá un mensaje de error y no podrá conectarse hasta que esté disponible otra conexión.</span><span class="sxs-lookup"><span data-stu-id="3a31f-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a31f-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3a31f-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a31f-131">Permisos</span><span class="sxs-lookup"><span data-stu-id="3a31f-131">Permissions</span></span>  
 <span data-ttu-id="3a31f-132">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="3a31f-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="3a31f-133">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3a31f-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="3a31f-134">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="3a31f-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a31f-135">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a31f-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="3a31f-136">Para configurar la opción de conexiones de usuario</span><span class="sxs-lookup"><span data-stu-id="3a31f-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="3a31f-137">En el Explorador de objetos, haga clic con el botón derecho en un servidor y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3a31f-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3a31f-138">Haga clic en el nodo **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="3a31f-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="3a31f-139">En **Conexiones**, en el cuadro **Número máximo de conexiones simultáneas** , escriba o seleccione un valor entre 0 y 32767 para establecer el número máximo de usuarios que se pueden conectar simultáneamente a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a31f-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="3a31f-140">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a31f-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3a31f-141">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a31f-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="3a31f-142">Para configurar la opción de conexiones de usuario</span><span class="sxs-lookup"><span data-stu-id="3a31f-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="3a31f-143">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a31f-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a31f-144">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3a31f-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a31f-145">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3a31f-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3a31f-146">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar el valor de la opción de `user connections` en `325` usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a31f-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="3a31f-147">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3a31f-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a> <span data-ttu-id="3a31f-148">Seguimiento: Después de configurar la opción de conexiones de usuario</span><span class="sxs-lookup"><span data-stu-id="3a31f-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="3a31f-149">El servidor debe reiniciarse para que el valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="3a31f-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a31f-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a31f-150">See Also</span></span>  
 <span data-ttu-id="3a31f-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a31f-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="3a31f-152">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a31f-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="3a31f-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3a31f-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
