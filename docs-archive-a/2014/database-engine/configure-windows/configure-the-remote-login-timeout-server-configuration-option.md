---
title: Establecer la opción de configuración del servidor Tiempo de espera de inicio de sesión remoto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663696"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="a5589-102">Establecer la opción de configuración del servidor Tiempo de espera de inicio de sesión remoto</span><span class="sxs-lookup"><span data-stu-id="a5589-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="a5589-103">En este tema se describe cómo configurar la opción de configuración de **tiempo de espera de inicio de sesión remoto** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5589-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a5589-104">La opción de **tiempo de espera de inicio de sesión remoto** especifica el número de segundos que se esperará para volver de un error al intentar el inicio de sesión en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="a5589-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="a5589-105">Por ejemplo, si intenta iniciar sesión en un servidor remoto y el servidor no está activo, la opción de **tiempo de espera de inicio de sesión remoto** le ayuda a asegurarse de no tener que esperar indefinidamente hasta que el equipo deje de intentar iniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a5589-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="a5589-106">El valor predeterminado para esta opción es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a5589-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="a5589-107">Un valor 0 permite una espera infinita.</span><span class="sxs-lookup"><span data-stu-id="a5589-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5589-108">El valor predeterminado para esta opción es de 20 segundos en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5589-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="a5589-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a5589-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a5589-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a5589-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a5589-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a5589-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a5589-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a5589-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a5589-113">**Para configurar la opción de tiempo de espera de inicio de sesión remoto, use:**</span><span class="sxs-lookup"><span data-stu-id="a5589-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="a5589-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5589-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a5589-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5589-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a5589-116">**Seguimiento:**  [Después de configurar la opción de tiempo de espera de inicio de sesión remoto](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a5589-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5589-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a5589-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a5589-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a5589-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a5589-119">La opción de **tiempo de espera de inicio de sesión remoto** afecta a las conexiones a proveedores OLE DB establecidas para realizar consultas heterogéneas.</span><span class="sxs-lookup"><span data-stu-id="a5589-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5589-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a5589-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a5589-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="a5589-121">Permissions</span></span>  
 <span data-ttu-id="a5589-122">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="a5589-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a5589-123">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a5589-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a5589-124">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="a5589-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a5589-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5589-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="a5589-126">Para configurar la opción de tiempo de espera de inicio de sesión remoto</span><span class="sxs-lookup"><span data-stu-id="a5589-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="a5589-127">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a5589-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a5589-128">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="a5589-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="a5589-129">En **Red**, seleccione un valor para el cuadro **Remote Login Timeout** .</span><span class="sxs-lookup"><span data-stu-id="a5589-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="a5589-130">Use la opción de **tiempo de espera de inicio de sesión remoto** para especificar el número de segundos que se esperará para volver cuando se produce un error al intentar un inicio de sesión remoto.</span><span class="sxs-lookup"><span data-stu-id="a5589-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a5589-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5589-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="a5589-132">Para configurar la opción de tiempo de espera de inicio de sesión remoto</span><span class="sxs-lookup"><span data-stu-id="a5589-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="a5589-133">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5589-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5589-134">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a5589-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a5589-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a5589-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a5589-136">Este ejemplo muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción `remote login timeout` en `35` segundos.</span><span class="sxs-lookup"><span data-stu-id="a5589-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="a5589-137">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5589-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="a5589-138">Seguimiento: Después de configurar la opción de tiempo de espera de inicio de sesión remoto</span><span class="sxs-lookup"><span data-stu-id="a5589-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="a5589-139">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="a5589-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5589-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5589-140">See Also</span></span>  
 <span data-ttu-id="a5589-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5589-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a5589-142">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a5589-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a5589-143">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5589-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
