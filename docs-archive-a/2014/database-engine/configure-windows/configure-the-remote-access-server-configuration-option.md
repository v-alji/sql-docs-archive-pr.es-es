---
title: Configurar la opción de configuración del servidor Acceso remoto | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663699"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="95db4-102">Configurar la opción de configuración del servidor Acceso remoto</span><span class="sxs-lookup"><span data-stu-id="95db4-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="95db4-103">En este tema se describe cómo establecer la opción de configuración del servidor **acceso remoto** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95db4-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="95db4-104">La opción **acceso remoto** controla la ejecución de los procedimientos almacenados desde servidores remotos o locales en los que se están ejecutando instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95db4-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="95db4-105">El valor predeterminado para esta opción es 1.</span><span class="sxs-lookup"><span data-stu-id="95db4-105">This default value for this option is 1.</span></span> <span data-ttu-id="95db4-106">Este valor concede el permiso para ejecutar los procedimientos almacenados locales desde servidores remotos o los procedimientos almacenados remotos desde el servidor local.</span><span class="sxs-lookup"><span data-stu-id="95db4-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="95db4-107">Para evitar que los procedimientos almacenados locales se ejecuten desde un servidor remoto o que los procedimientos almacenados remotos se ejecuten desde un servidor local, establezca la opción en 0.</span><span class="sxs-lookup"><span data-stu-id="95db4-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="95db4-108">Use en su lugar [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95db4-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="95db4-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="95db4-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="95db4-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="95db4-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="95db4-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="95db4-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="95db4-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="95db4-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="95db4-113">**Para configurar la opción de acceso remoto, use:**</span><span class="sxs-lookup"><span data-stu-id="95db4-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="95db4-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95db4-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="95db4-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95db4-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="95db4-116">**Seguimiento:**  [Después de configurar la opción de acceso remoto](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="95db4-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="95db4-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="95db4-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="95db4-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="95db4-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="95db4-119">La opción de **acceso remoto** solo se aplica a los servidores agregados mediante [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)y se incluye por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="95db4-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="95db4-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="95db4-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="95db4-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="95db4-121">Permissions</span></span>  
 <span data-ttu-id="95db4-122">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="95db4-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="95db4-123">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="95db4-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="95db4-124">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="95db4-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="95db4-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95db4-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="95db4-126">Para configurar la opción de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="95db4-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="95db4-127">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="95db4-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="95db4-128">Haga clic en el nodo **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="95db4-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="95db4-129">En **Conexiones a servidores remotos**, active o desactive la casilla **Permitir conexiones remotas con este servidor** .</span><span class="sxs-lookup"><span data-stu-id="95db4-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="95db4-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95db4-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="95db4-131">Para configurar la opción de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="95db4-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="95db4-132">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95db4-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="95db4-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="95db4-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="95db4-134">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="95db4-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="95db4-135">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `remote access` en `0`.</span><span class="sxs-lookup"><span data-stu-id="95db4-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="95db4-136">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="95db4-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a> <span data-ttu-id="95db4-137">Seguimiento: Después de configurar la opción de acceso remoto</span><span class="sxs-lookup"><span data-stu-id="95db4-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="95db4-138">Esta configuración no surte efecto hasta que reinicie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95db4-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95db4-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95db4-139">See Also</span></span>  
 <span data-ttu-id="95db4-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95db4-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="95db4-141">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95db4-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="95db4-142">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95db4-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
