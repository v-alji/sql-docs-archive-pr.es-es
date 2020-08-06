---
title: Establecer la opción de configuración del servidor Desencadenadores anidados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674339"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="733c2-102">Establecer la opción de configuración del servidor Desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="733c2-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="733c2-103">En este tema se describe cómo establecer la opción de configuración del servidor **desencadenadores anidados** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="733c2-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="733c2-104">La opción de **desencadenadores anidados** controla si un desencadenador AFTER puede actuar en cascada.</span><span class="sxs-lookup"><span data-stu-id="733c2-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="733c2-105">Es decir, realizar una acción que inicia otro desencadenador, que inicia otro desencadenador, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="733c2-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="733c2-106">Si establece el valor 0 para **nested triggers** , los desencadenadores AFTER no podrán actuar en cascada.</span><span class="sxs-lookup"><span data-stu-id="733c2-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="733c2-107">En cambio, si el valor de la opción **nested triggers** es 1 (el valor predeterminado), los desencadenadores AFTER podrán actuar en cascada hasta un máximo de 32 niveles.</span><span class="sxs-lookup"><span data-stu-id="733c2-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="733c2-108">Los desencadenadores INSTEAD OF se pueden anidar, independientemente del valor de esta opción.</span><span class="sxs-lookup"><span data-stu-id="733c2-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="733c2-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="733c2-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="733c2-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="733c2-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="733c2-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="733c2-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="733c2-112">**Para configurar la opción de desencadenadores anidados, use:**</span><span class="sxs-lookup"><span data-stu-id="733c2-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="733c2-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="733c2-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="733c2-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="733c2-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="733c2-115">**Seguimiento:**  [Después de configurar la opción de desencadenadores anidados](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="733c2-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="733c2-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="733c2-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="733c2-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="733c2-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="733c2-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="733c2-118">Permissions</span></span>  
 <span data-ttu-id="733c2-119">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="733c2-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="733c2-120">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="733c2-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="733c2-121">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="733c2-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="733c2-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="733c2-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="733c2-123">Para configurar la opción de desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="733c2-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="733c2-124">En el **Explorador de objetos**, haga clic con el botón derecho en un servidor y luego seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="733c2-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="733c2-125">En la página **Avanzadas** , establezca la opción **Permitir que los desencadenadores activen otros** en **True** (el valor predeterminado) o **False**.</span><span class="sxs-lookup"><span data-stu-id="733c2-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="733c2-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="733c2-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="733c2-127">Para configurar la opción de desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="733c2-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="733c2-128">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="733c2-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="733c2-129">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="733c2-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="733c2-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="733c2-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="733c2-131">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `nested triggers` en `0`.</span><span class="sxs-lookup"><span data-stu-id="733c2-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="733c2-132">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="733c2-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a> <span data-ttu-id="733c2-133">Seguimiento: Después de configurar la opción de desencadenadores anidados</span><span class="sxs-lookup"><span data-stu-id="733c2-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="733c2-134">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="733c2-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733c2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="733c2-135">See Also</span></span>  
 <span data-ttu-id="733c2-136">[Crear desencadenadores anidados](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="733c2-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="733c2-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="733c2-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="733c2-138">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="733c2-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="733c2-139">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="733c2-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
