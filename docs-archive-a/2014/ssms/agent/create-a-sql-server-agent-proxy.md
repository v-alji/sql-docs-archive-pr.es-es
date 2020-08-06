---
title: Crear un proxy del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675109"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="04715-102">Create a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="04715-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="04715-103">En este tema se describe cómo crea un proxy del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04715-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="04715-104">Una cuenta de proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] define un contexto de seguridad en el que es posible ejecutar un paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04715-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="04715-105">Cada proxy se corresponde con unas credenciales de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04715-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="04715-106">Para establecer los permisos para un paso de trabajo concreto, cree un proxy que disponga de los permisos necesarios para un subsistema del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, a continuación, asigne ese proxy al paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04715-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="04715-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="04715-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="04715-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="04715-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="04715-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="04715-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="04715-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04715-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="04715-111">**Para crear un proxy del Agente SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="04715-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="04715-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04715-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="04715-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04715-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="04715-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="04715-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="04715-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="04715-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="04715-116">Debe crear una credencial antes de crear un proxy si todavía no hay uno disponible.</span><span class="sxs-lookup"><span data-stu-id="04715-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="04715-117">Las cuentas de proxy del Agente[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizan credenciales para almacenar información acerca de las cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="04715-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="04715-118">El usuario especificado en las credenciales debe tener el permiso "Iniciar sesión como proceso por lotes" en el equipo en que se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04715-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04715-119">comprueba el acceso al subsistema de un proxy y da acceso al proxy cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04715-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="04715-120">Si el proxy ya no tiene acceso al subsistema, el paso de trabajo da error.</span><span class="sxs-lookup"><span data-stu-id="04715-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="04715-121">De lo contrario, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suplanta al usuario especificado en el proxy y ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04715-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="04715-122">La creación de un proxy no cambia los permisos del usuario especificado en las credenciales del proxy.</span><span class="sxs-lookup"><span data-stu-id="04715-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="04715-123">Por ejemplo, puede crear un proxy para un usuario que no tiene permisos para conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04715-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="04715-124">En este caso, los pasos de trabajo que usan el proxy no pueden conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04715-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="04715-125">Si el inicio de sesión del usuario tiene acceso al proxy o si el usuario pertenece a un rol con acceso al proxy, puede usarlo en un paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04715-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04715-126">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04715-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="04715-127">Permisos</span><span class="sxs-lookup"><span data-stu-id="04715-127">Permissions</span></span>  
  
-   <span data-ttu-id="04715-128">Solo los miembros del rol fijo de servidor **sysadmin** disponen del permiso necesario para crear, modificar o eliminar cuentas de proxy.</span><span class="sxs-lookup"><span data-stu-id="04715-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="04715-129">Los usuarios que no son miembros del rol fijo de servidor **sysadmin** deben agregarse a uno de los siguientes roles fijos de base de datos del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos **msdb** para usar los servidores proxy: **SQLAgentUserRole**, **SQLAgentReaderRole**o **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="04715-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="04715-130">Requiere el permiso `ALTER ANY CREDENTIAL` si crea una credencial además del proxy.</span><span class="sxs-lookup"><span data-stu-id="04715-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="04715-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04715-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="04715-132">Para crear un proxy del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="04715-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="04715-133">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea crear un proxy del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04715-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="04715-134">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="04715-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="04715-135">Haga clic con el botón derecho en la carpeta **Servidores proxy** y seleccione **Nuevo proxy**.</span><span class="sxs-lookup"><span data-stu-id="04715-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="04715-136">En del cuadro de diálogo **Nueva cuenta de proxy** , en la página **General** , especifique el nombre de la cuenta de proxy en el cuadro **Nombre del proxy** .</span><span class="sxs-lookup"><span data-stu-id="04715-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="04715-137">En el cuadro **Nombre de credencial** , escriba el nombre de la credencial de seguridad que la cuenta de proxy utilizará.</span><span class="sxs-lookup"><span data-stu-id="04715-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="04715-138">En el cuadro de **Descripción** , escriba una descripción de la cuenta de proxy</span><span class="sxs-lookup"><span data-stu-id="04715-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="04715-139">En **Activar para los subsistemas siguientes**, seleccione el subsistema o los subsistemas apropiados para este proxy.</span><span class="sxs-lookup"><span data-stu-id="04715-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="04715-140">En la página **Entidades de seguridad** , agregue o quite inicios de sesión o roles para conceder o quitar el acceso a la cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="04715-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="04715-141">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04715-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="04715-142">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04715-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="04715-143">Para crear un proxy del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="04715-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="04715-144">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04715-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="04715-145">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="04715-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="04715-146">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="04715-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="04715-147">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="04715-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="04715-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04715-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="04715-149">sp_add_proxy &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04715-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="04715-150">sp_grant_proxy_to_subsystem &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04715-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
