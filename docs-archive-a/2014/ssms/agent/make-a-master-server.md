---
title: Establecer un servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672351"
---
# <a name="make-a-master-server"></a><span data-ttu-id="8546c-102">Make a Master Server</span><span class="sxs-lookup"><span data-stu-id="8546c-102">Make a Master Server</span></span>
  <span data-ttu-id="8546c-103">En este tema se describe cómo establecer un servidor maestro de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8546c-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8546c-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8546c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8546c-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8546c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8546c-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8546c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8546c-107">**Para establecer un servidor maestro, usando:**</span><span class="sxs-lookup"><span data-stu-id="8546c-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="8546c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8546c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8546c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8546c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8546c-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8546c-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8546c-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8546c-111">Security</span></span>  
 <span data-ttu-id="8546c-112">Los trabajos distribuidos que tienen pasos asociados a un proxy se ejecutan bajo el contexto de la cuenta de proxy en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="8546c-113">Para que se descarguen del servidor maestro al de destino los pasos de trabajo asociados con un proxy, asegúrese de que se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8546c-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="8546c-114">La subclave del registro del servidor maestro **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \sql Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) está establecida en 1 (true).</span><span class="sxs-lookup"><span data-stu-id="8546c-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="8546c-115">De forma predeterminada, esta subclave está establecida en 0 (false).</span><span class="sxs-lookup"><span data-stu-id="8546c-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="8546c-116">Existe una cuenta de proxy en el servidor de destino que tiene el mismo nombre que la cuenta de proxy del servidor maestro bajo el que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8546c-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="8546c-117">Si se producen errores en los pasos de trabajo que utilizan cuentas de proxy durante la descarga de éstos desde el servidor maestro al servidor de destino, puede buscar en la columna **error_message** de la tabla **sysdownloadlist** de la base de datos **msdb** los mensajes de error que digan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8546c-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="8546c-118">"Este trabajo requiere una cuenta de proxy, pero la coincidencia de proxy se ha deshabilitado en el servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="8546c-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="8546c-119">Para resolver este error, establezca la subclave de registro **AllowDownloadedJobsToMatchProxyName** en 1.</span><span class="sxs-lookup"><span data-stu-id="8546c-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="8546c-120">"No se encontró el proxy".</span><span class="sxs-lookup"><span data-stu-id="8546c-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="8546c-121">Para resolver este error, asegúrese de que existe una cuenta de proxy en el servidor de destino con el mismo nombre que la cuenta de proxy del servidor maestro en la que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8546c-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8546c-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="8546c-122">Permissions</span></span>  
 <span data-ttu-id="8546c-123">Los permisos de ejecución de este procedimiento corresponden de forma predeterminada a los miembros del rol fijo de servidor `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="8546c-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8546c-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8546c-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="8546c-125">Para establecer un servidor principal</span><span class="sxs-lookup"><span data-stu-id="8546c-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="8546c-126">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="8546c-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8546c-127">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración de multiservidor**y, a continuación, haga clic en **Hacer que sea principal**.</span><span class="sxs-lookup"><span data-stu-id="8546c-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="8546c-128">El **Asistente para servidor principal** le guiará en el proceso de establecimiento de un servidor principal y de adición de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="8546c-129">En la página **Operador del servidor maestro** , configure un operador para el servidor maestro. Para enviar notificaciones a los operadores mediante correo electrónico o buscapersonas, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe estar configurado para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8546c-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="8546c-130">Para enviar notificaciones a los operadores mediante **net send**, el servicio Messenger debe estar en ejecución en el servidor donde reside el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8546c-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="8546c-131">**Dirección de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="8546c-131">**E-mail address**</span></span>  
     <span data-ttu-id="8546c-132">Establece la dirección de correo electrónico del operador.</span><span class="sxs-lookup"><span data-stu-id="8546c-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="8546c-133">**Dirección del buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="8546c-133">**Pager address**</span></span>  
     <span data-ttu-id="8546c-134">Establece la dirección de correo electrónico de buscapersonas para el operador.</span><span class="sxs-lookup"><span data-stu-id="8546c-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="8546c-135">**Dirección de NET SEND**</span><span class="sxs-lookup"><span data-stu-id="8546c-135">**Net send address**</span></span>  
     <span data-ttu-id="8546c-136">Establece la dirección de **net send** del operador.</span><span class="sxs-lookup"><span data-stu-id="8546c-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="8546c-137">En la página **Servidor de destino** , seleccione servidores de destino para el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="8546c-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="8546c-138">**Servidores registrados**</span><span class="sxs-lookup"><span data-stu-id="8546c-138">**Registered Servers**</span></span>  
     <span data-ttu-id="8546c-139">Muestra los servidores registrados en Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] que todavía no son servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="8546c-140">**Servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="8546c-140">**Target Servers**</span></span>  
     <span data-ttu-id="8546c-141">Muestra los servidores que son servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="8546c-142">Mueve el servidor seleccionado a la lista de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="8546c-143">Mueve todos los servidores a la lista de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="8546c-144">Quita el servidor seleccionado de la lista de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="8546c-145">Quita todos los servidores de la lista de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8546c-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="8546c-146">**Agregar conexión**</span><span class="sxs-lookup"><span data-stu-id="8546c-146">**Add connection**</span></span>  
     <span data-ttu-id="8546c-147">Agrega un servidor a la lista de servidores de destino sin registrarlo.</span><span class="sxs-lookup"><span data-stu-id="8546c-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="8546c-148">**Connection**</span><span class="sxs-lookup"><span data-stu-id="8546c-148">**Connection**</span></span>  
     <span data-ttu-id="8546c-149">Cambia las propiedades de conexión del servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8546c-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="8546c-150">En la página **Credenciales de inicio de sesión del servidor maestro** , especifique si desea crear un nuevo inicio de sesión para el servidor de destino, si es necesario, y asignarle derechos de acceso al servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="8546c-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="8546c-151">**Cree un nuevo inicio de sesión, si es necesario, y asígnele derechos para el servidor maestro**</span><span class="sxs-lookup"><span data-stu-id="8546c-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="8546c-152">Crea un nuevo inicio de sesión en el servidor de destino si el inicio de sesión especificado ya no existe.</span><span class="sxs-lookup"><span data-stu-id="8546c-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8546c-153">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8546c-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="8546c-154">Para establecer un servidor principal</span><span class="sxs-lookup"><span data-stu-id="8546c-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="8546c-155">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8546c-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8546c-156">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="8546c-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8546c-157">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8546c-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8546c-158">En este ejemplo se da de alta el servidor actual en el servidor maestro AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="8546c-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="8546c-159">La ubicación del servidor actual es Building 21, Room 309, Rack 5.</span><span class="sxs-lookup"><span data-stu-id="8546c-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="8546c-160">Para obtener más información, vea [sp_msx_enlist &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8546c-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8546c-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8546c-161">See Also</span></span>  
 <span data-ttu-id="8546c-162">[Crear un entorno multiservidor](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="8546c-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="8546c-163">Administración automatizada en una empresa</span><span class="sxs-lookup"><span data-stu-id="8546c-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
