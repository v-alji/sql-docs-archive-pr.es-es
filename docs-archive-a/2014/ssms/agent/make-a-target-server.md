---
title: Establecer un servidor de destino | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743908"
---
# <a name="make-a-target-server"></a><span data-ttu-id="f9e06-102">Establecer un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="f9e06-102">Make a Target Server</span></span>
  <span data-ttu-id="f9e06-103">En este tema se describe cómo establecer un servidor de destino en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="f9e06-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="f9e06-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f9e06-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f9e06-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f9e06-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f9e06-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f9e06-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f9e06-107">**Para establecer un servidor de destino, usando**</span><span class="sxs-lookup"><span data-stu-id="f9e06-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="f9e06-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9e06-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f9e06-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9e06-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="f9e06-110">SMO</span><span class="sxs-lookup"><span data-stu-id="f9e06-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f9e06-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f9e06-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f9e06-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f9e06-112">Security</span></span>  
 <span data-ttu-id="f9e06-113">Los trabajos distribuidos que tienen pasos asociados a un proxy se ejecutan bajo el contexto de la cuenta de proxy en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="f9e06-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="f9e06-114">Para que se descarguen del servidor maestro al de destino los pasos de trabajo asociados con un proxy, asegúrese de que se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9e06-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="f9e06-115">La subclave del registro del servidor maestro **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \sql Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) está establecida en 1 (true).</span><span class="sxs-lookup"><span data-stu-id="f9e06-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="f9e06-116">De forma predeterminada, esta subclave está establecida en 0 (false).</span><span class="sxs-lookup"><span data-stu-id="f9e06-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="f9e06-117">Existe una cuenta de proxy en el servidor de destino que tiene el mismo nombre que la cuenta de proxy del servidor maestro bajo el que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f9e06-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="f9e06-118">Si se producen errores en los pasos de trabajo que utilizan cuentas de proxy durante la descarga de éstos desde el servidor maestro al servidor de destino, puede buscar en la columna **error_message** de la tabla **sysdownloadlist** de la base de datos **msdb** los mensajes de error que digan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9e06-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="f9e06-119">"Este trabajo requiere una cuenta de proxy, pero la coincidencia de proxy se ha deshabilitado en el servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="f9e06-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="f9e06-120">Para resolver este error, establezca la subclave de registro **AllowDownloadedJobsToMatchProxyName** en 1.</span><span class="sxs-lookup"><span data-stu-id="f9e06-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="f9e06-121">"No se encontró el proxy".</span><span class="sxs-lookup"><span data-stu-id="f9e06-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="f9e06-122">Para resolver este error, asegúrese de que existe una cuenta de proxy en el servidor de destino con el mismo nombre que la cuenta de proxy del servidor maestro en la que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f9e06-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f9e06-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="f9e06-123">Permissions</span></span>  
 <span data-ttu-id="f9e06-124">Los permisos de ejecución de este procedimiento corresponden de forma predeterminada a los miembros del rol fijo de servidor `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="f9e06-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f9e06-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9e06-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="f9e06-126">Para establecer un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="f9e06-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="f9e06-127">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="f9e06-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f9e06-128">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración de multiservidor**y, luego, haga clic en **Establecer como destino**.</span><span class="sxs-lookup"><span data-stu-id="f9e06-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="f9e06-129">El **Asistente para establecer servidor de destino** le guiará en el proceso de establecimiento de un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="f9e06-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="f9e06-130">En la página **Seleccionar un servidor maestro** , seleccione el servidor maestro del que este servidor de destino recibirá trabajos.</span><span class="sxs-lookup"><span data-stu-id="f9e06-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="f9e06-131">**Seleccionar servidor**</span><span class="sxs-lookup"><span data-stu-id="f9e06-131">**Pick Server**</span></span>  
     <span data-ttu-id="f9e06-132">Conéctese al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="f9e06-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="f9e06-133">**Descripción de este servidor**</span><span class="sxs-lookup"><span data-stu-id="f9e06-133">**Description of this server**</span></span>  
     <span data-ttu-id="f9e06-134">Escriba una descripción para este servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="f9e06-134">Type a description for this target server.</span></span> <span data-ttu-id="f9e06-135">El servidor de destino carga esta descripción en el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="f9e06-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="f9e06-136">En la página **Credenciales de inicio de sesión del servidor maestro** , cree un nuevo inicio de sesión en el servidor de destino, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f9e06-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="f9e06-137">**Cree un nuevo inicio de sesión, si es necesario, y asígnele derechos para el servidor maestro**</span><span class="sxs-lookup"><span data-stu-id="f9e06-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="f9e06-138">Crea un nuevo inicio de sesión en el servidor de destino si el inicio de sesión especificado ya no existe.</span><span class="sxs-lookup"><span data-stu-id="f9e06-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f9e06-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9e06-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="f9e06-140">Para establecer un servidor de destino</span><span class="sxs-lookup"><span data-stu-id="f9e06-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="f9e06-141">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9e06-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f9e06-142">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f9e06-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f9e06-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f9e06-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f9e06-144">En este ejemplo se da de alta el servidor actual en el servidor maestro AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="f9e06-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="f9e06-145">La ubicación del servidor actual es Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="f9e06-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="f9e06-146">Para obtener más información, vea [sp_msx_enlist &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f9e06-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="f9e06-147">Usar Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="f9e06-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e06-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9e06-148">See Also</span></span>  
 [<span data-ttu-id="f9e06-149">Administración automatizada en una empresa</span><span class="sxs-lookup"><span data-stu-id="f9e06-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
