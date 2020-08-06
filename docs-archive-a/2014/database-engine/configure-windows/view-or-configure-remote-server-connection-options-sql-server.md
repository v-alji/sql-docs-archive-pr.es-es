---
title: Ver o configurar las opciones de conexión de servidor remoto (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744851"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="73b90-102">Ver o configurar las opciones de conexión de servidor remoto (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="73b90-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="73b90-103">En este tema se describe cómo ver o configurar las opciones de conexión de servidor remoto en el nivel de servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73b90-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="73b90-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="73b90-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="73b90-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="73b90-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="73b90-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="73b90-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="73b90-107">**Para ver o configurar las opciones de conexión de servidor remoto, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="73b90-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="73b90-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="73b90-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="73b90-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73b90-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="73b90-110">**Seguimiento:**  [después de configurar las opciones de conexión de servidor remoto](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="73b90-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="73b90-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="73b90-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="73b90-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="73b90-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="73b90-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="73b90-113">Permissions</span></span>  
 <span data-ttu-id="73b90-114">La ejecución de **sp_serveroption** requiere el permiso ALTER ANY LINKED SERVER en el servidor.</span><span class="sxs-lookup"><span data-stu-id="73b90-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="73b90-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="73b90-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="73b90-116">Para ver o configurar las opciones de conexión de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="73b90-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="73b90-117">En el Explorador de objetos, haga clic con el botón derecho en un servidor y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="73b90-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="73b90-118">En el cuadro de diálogo **Propiedades de SQL Server: \<***server_name***>** , haga clic en **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="73b90-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="73b90-119">En la página **Conexiones** , revise las opciones de configuración de **Conexiones a servidores remotos** y modifíquelas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="73b90-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="73b90-120">Repita los pasos 1 a 3 en el otro servidor de la pareja de servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="73b90-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="73b90-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73b90-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="73b90-122">Para ver las opciones de conexión de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="73b90-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="73b90-123">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73b90-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="73b90-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="73b90-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="73b90-125">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="73b90-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="73b90-126">En este ejemplo se usa [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) para devolver información sobre todos los servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="73b90-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="73b90-127">Para configurar las opciones de conexión de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="73b90-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="73b90-128">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73b90-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="73b90-129">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="73b90-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="73b90-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="73b90-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="73b90-131">En este ejemplo se muestra cómo usar [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) para configurar un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="73b90-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="73b90-132">En el ejemplo siguiente se configura un servidor remoto que corresponde a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, para que sea compatible con la intercalación de la instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73b90-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a> <span data-ttu-id="73b90-133">Seguimiento: después de configurar las opciones de conexión de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="73b90-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="73b90-134">El servidor remoto debe detenerse e reiniciarse para que la opción de configuración valor surta efecto.</span><span class="sxs-lookup"><span data-stu-id="73b90-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b90-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73b90-135">See Also</span></span>  
 <span data-ttu-id="73b90-136">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="73b90-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="73b90-137">[Servidores remotos](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="73b90-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="73b90-138">[Servidores vinculados &#40;motor de base de datos&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="73b90-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="73b90-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73b90-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="73b90-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73b90-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="73b90-141">sp_serveroption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73b90-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  
