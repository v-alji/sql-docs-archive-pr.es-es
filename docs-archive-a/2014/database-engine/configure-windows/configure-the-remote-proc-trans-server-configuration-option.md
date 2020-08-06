---
title: Establecer la opción de configuración del servidor Transacciones de procedimientos remotos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671163"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="d3684-102">Establecer la opción de configuración del servidor Transacciones de procedimientos remotos</span><span class="sxs-lookup"><span data-stu-id="d3684-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="d3684-103">En este tema se describe cómo establecer la opción de configuración del servidor **transacciones de procedimientos remotos** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3684-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d3684-104">La opción **transacciones de procedimientos remotos** ayuda a proteger las acciones de un procedimiento entre servidores por medio de una transacción del Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="d3684-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="d3684-105">Establezca el valor de **transacciones de procedimientos remotos** en 1 para proporcionar una transacción distribuida coordinada con MS DTC que proteja las propiedades ACID (atómicas, coherentes, aisladas y duraderas) de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="d3684-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="d3684-106">Las sesiones que han comenzado después de establecer el valor 1 para esta opción heredan el valor de la configuración como el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d3684-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="d3684-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d3684-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d3684-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d3684-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d3684-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d3684-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d3684-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="d3684-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d3684-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d3684-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d3684-112">**Para configurar la opción de transacciones de procedimientos remotos, use:**</span><span class="sxs-lookup"><span data-stu-id="d3684-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="d3684-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3684-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d3684-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d3684-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d3684-115">**Seguimiento:**  [Después de configurar la opción de transacciones de procedimientos remotos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d3684-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d3684-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d3684-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d3684-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d3684-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="d3684-118">Deben permitirse conexiones de servidor remoto para poder establecer este valor.</span><span class="sxs-lookup"><span data-stu-id="d3684-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d3684-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="d3684-119">Recommendations</span></span>  
  
-   <span data-ttu-id="d3684-120">Esta opción se ofrece por motivos de compatibilidad con versiones anteriores de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para las aplicaciones que usan procedimientos almacenados remotos.</span><span class="sxs-lookup"><span data-stu-id="d3684-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="d3684-121">En lugar de emitir llamadas a procedimientos almacenados remotos, use consultas distribuidas que hagan referencia a servidores vinculados, que se definen por medio de [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d3684-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d3684-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d3684-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d3684-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="d3684-123">Permissions</span></span>  
 <span data-ttu-id="d3684-124">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="d3684-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d3684-125">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d3684-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d3684-126">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="d3684-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d3684-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3684-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="d3684-128">Para configurar la opción de transacciones de procedimientos remotos</span><span class="sxs-lookup"><span data-stu-id="d3684-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="d3684-129">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d3684-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d3684-130">Haga clic en el nodo **Conexiones** .</span><span class="sxs-lookup"><span data-stu-id="d3684-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="d3684-131">En **Conexiones a servidores remotos**, active la casilla **Exigir transacciones distribuidas para comunicación entre servidores** .</span><span class="sxs-lookup"><span data-stu-id="d3684-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d3684-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d3684-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="d3684-133">Para configurar la opción de transacciones de procedimientos remotos</span><span class="sxs-lookup"><span data-stu-id="d3684-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="d3684-134">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3684-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d3684-135">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d3684-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d3684-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d3684-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d3684-137">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `remote proc trans` en `1`.</span><span class="sxs-lookup"><span data-stu-id="d3684-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="d3684-138">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3684-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a> <span data-ttu-id="d3684-139">Seguimiento: Después de configurar la opción de transacciones de procedimientos remotos</span><span class="sxs-lookup"><span data-stu-id="d3684-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="d3684-140">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="d3684-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3684-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3684-141">See Also</span></span>  
 <span data-ttu-id="d3684-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d3684-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d3684-143">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d3684-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d3684-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d3684-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
