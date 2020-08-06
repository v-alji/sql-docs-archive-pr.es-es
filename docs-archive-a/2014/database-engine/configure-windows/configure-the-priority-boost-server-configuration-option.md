---
title: Establecer la opción de configuración del servidor Aumento de prioridad | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671166"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="ce239-102">Establecer la opción de configuración del servidor Aumento de prioridad</span><span class="sxs-lookup"><span data-stu-id="ce239-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="ce239-103">En este tema se describe cómo configurar la opción de configuración de **aumento de prioridad** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce239-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ce239-104">Use la opción **Aumento de prioridad** para especificar si [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ejecutarse con una prioridad de programación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 o Windows 2008 R2 superior a la de otros procesos del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="ce239-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="ce239-105">Si establece esta opción en 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecutará con una prioridad base de 13 en el programador de Windows 2008 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="ce239-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="ce239-106">El valor predeterminado es 0, que equivale a una prioridad base de 7.</span><span class="sxs-lookup"><span data-stu-id="ce239-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="ce239-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ce239-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ce239-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ce239-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ce239-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ce239-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ce239-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ce239-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ce239-111">**Para configurar la opción de aumento de prioridad, use:**</span><span class="sxs-lookup"><span data-stu-id="ce239-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="ce239-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce239-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ce239-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce239-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ce239-114">**Seguimiento:**  [Después de configurar la opción de aumento de prioridad](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ce239-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ce239-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ce239-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ce239-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ce239-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ce239-117">El aumento excesivo de la prioridad puede reducir los recursos para funciones fundamentales de la red y del sistema operativo, lo que causaría problemas al cerrar SQL Server o al usar otras tareas del sistema operativo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ce239-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ce239-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ce239-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ce239-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="ce239-119">Permissions</span></span>  
 <span data-ttu-id="ce239-120">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="ce239-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ce239-121">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ce239-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ce239-122">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="ce239-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ce239-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce239-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="ce239-124">Para configurar la opción de aumento de prioridad</span><span class="sxs-lookup"><span data-stu-id="ce239-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="ce239-125">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ce239-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ce239-126">Haga clic en el nodo **Procesadores** .</span><span class="sxs-lookup"><span data-stu-id="ce239-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="ce239-127">En **Subprocesos**, active la casilla **Aumentar la prioridad de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="ce239-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="ce239-128">Detenga y reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce239-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ce239-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce239-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="ce239-130">Para configurar la opción de aumento de prioridad</span><span class="sxs-lookup"><span data-stu-id="ce239-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="ce239-131">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce239-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ce239-132">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ce239-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ce239-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ce239-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ce239-134">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `priority boost` en `1`.</span><span class="sxs-lookup"><span data-stu-id="ce239-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="ce239-135">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ce239-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a> <span data-ttu-id="ce239-136">Seguimiento: Después de configurar la opción de aumento de prioridad</span><span class="sxs-lookup"><span data-stu-id="ce239-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="ce239-137">El servidor debe reiniciarse para que el valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="ce239-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce239-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce239-138">See Also</span></span>  
 <span data-ttu-id="ce239-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ce239-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ce239-140">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce239-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ce239-141">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce239-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
