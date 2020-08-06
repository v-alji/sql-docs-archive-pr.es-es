---
title: Establecer la opción de configuración del servidor Idioma predeterminado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750150"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="78d1a-102">Establecer la opción de configuración del servidor Idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="78d1a-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="78d1a-103">En este tema se describe cómo configurar la opción de configuración de servidor **idioma predeterminado** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78d1a-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78d1a-104">La opción de **idioma predeterminado** especifica el idioma predeterminado de todos los inicios de sesión de nueva creación.</span><span class="sxs-lookup"><span data-stu-id="78d1a-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="78d1a-105">Para establecer el idioma predeterminado, especifique el valor **langid** del idioma que desee.</span><span class="sxs-lookup"><span data-stu-id="78d1a-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="78d1a-106">El valor **langid** se obtiene consultando la vista de compatibilidad **sys.syslanguages** .</span><span class="sxs-lookup"><span data-stu-id="78d1a-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="78d1a-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="78d1a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78d1a-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="78d1a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78d1a-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="78d1a-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="78d1a-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="78d1a-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78d1a-111">**Para configurar la opción de idioma predeterminado, use:**</span><span class="sxs-lookup"><span data-stu-id="78d1a-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="78d1a-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78d1a-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78d1a-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78d1a-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="78d1a-114">**Seguimiento:**  [Después de configurar la opción de idioma predeterminado](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78d1a-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78d1a-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="78d1a-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="78d1a-116">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="78d1a-116">Recommendations</span></span>  
  
-   <span data-ttu-id="78d1a-117">El idioma predeterminado de un inicio de sesión se puede invalidar mediante CREATE LOGIN o ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="78d1a-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="78d1a-118">El idioma predeterminado de una sesión es el idioma del inicio de esa sesión, a menos que se reemplace para cada sesión mediante las API OLE DB o Conectividad abierta de bases de datos (ODBC).</span><span class="sxs-lookup"><span data-stu-id="78d1a-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="78d1a-119">Tenga en cuenta que solo puede establecer la opción **default language** con un identificador de idioma definido en [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span><span class="sxs-lookup"><span data-stu-id="78d1a-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="78d1a-120">Cuando se usan bases de datos independientes, se puede establecer un idioma predeterminado para una base de datos mediante CREATE DATABASE o ALTER DATABASE, y para los usuarios de las bases de datos independientes mediante CREATE USER o ALTER USER.</span><span class="sxs-lookup"><span data-stu-id="78d1a-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="78d1a-121">Al establecer los idiomas predeterminados de una base de datos independiente, se acepta el valor de **langid** , el nombre del idioma o el alias del idioma que aparece en **sys.syslanguages.**</span><span class="sxs-lookup"><span data-stu-id="78d1a-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78d1a-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="78d1a-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78d1a-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="78d1a-123">Permissions</span></span>  
 <span data-ttu-id="78d1a-124">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="78d1a-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="78d1a-125">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="78d1a-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="78d1a-126">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="78d1a-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78d1a-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78d1a-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="78d1a-128">Para configurar la opción de idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="78d1a-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="78d1a-129">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78d1a-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="78d1a-130">Haga clic en el nodo **Configuración adicional del servidor** .</span><span class="sxs-lookup"><span data-stu-id="78d1a-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="78d1a-131">En el cuadro **Idioma predeterminado para el usuario** , elija el idioma en que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe mostrar los mensajes del sistema.</span><span class="sxs-lookup"><span data-stu-id="78d1a-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="78d1a-132">El idioma predeterminado es el inglés.</span><span class="sxs-lookup"><span data-stu-id="78d1a-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78d1a-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78d1a-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="78d1a-134">Para configurar la opción de idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="78d1a-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="78d1a-135">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78d1a-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78d1a-136">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="78d1a-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78d1a-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="78d1a-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="78d1a-138">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar la opción de `default language` en Francés (`2`).</span><span class="sxs-lookup"><span data-stu-id="78d1a-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="78d1a-139">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78d1a-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="78d1a-140">Seguimiento: Después de configurar la opción de idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="78d1a-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="78d1a-141">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="78d1a-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d1a-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78d1a-142">See Also</span></span>  
 <span data-ttu-id="78d1a-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-147">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78d1a-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="78d1a-150">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="78d1a-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="78d1a-151">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78d1a-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
