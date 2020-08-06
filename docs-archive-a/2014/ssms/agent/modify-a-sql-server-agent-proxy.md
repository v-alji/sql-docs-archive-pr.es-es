---
title: Modificar un proxy del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671335"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="41295-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="41295-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="41295-103">En este tema se describe cómo modificar un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proxy del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41295-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="41295-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="41295-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="41295-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="41295-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="41295-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="41295-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="41295-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="41295-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="41295-108">**Para modificar un proxy del Agente SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="41295-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="41295-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41295-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="41295-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41295-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="41295-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="41295-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="41295-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="41295-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="41295-113">Las cuentas de proxy del Agente[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizan credenciales para almacenar información acerca de las cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="41295-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="41295-114">El usuario especificado en las credenciales debe tener el permiso "Iniciar sesión como proceso por lotes" en el equipo en que se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41295-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41295-115">comprueba el acceso al subsistema de un proxy y da acceso al proxy cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="41295-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="41295-116">Si el proxy ya no tiene acceso al subsistema, el paso de trabajo da error.</span><span class="sxs-lookup"><span data-stu-id="41295-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="41295-117">De lo contrario, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suplanta al usuario especificado en el proxy y ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="41295-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="41295-118">Si el inicio de sesión del usuario tiene acceso al proxy o si el usuario pertenece a un rol con acceso al proxy, puede usarlo en un paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="41295-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="41295-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="41295-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="41295-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="41295-120">Permissions</span></span>  
 <span data-ttu-id="41295-121">Solo los miembros del rol fijo de servidor **sysadmin** pueden crear, modificar o eliminar cuentas de proxy.</span><span class="sxs-lookup"><span data-stu-id="41295-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="41295-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41295-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="41295-123">Para modificar un proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41295-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="41295-124">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la cuenta de proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="41295-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="41295-125">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="41295-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="41295-126">Haga clic en el signo más para expandir la carpeta **Servidores proxy** .</span><span class="sxs-lookup"><span data-stu-id="41295-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="41295-127">Haga clic en el signo más para expandir el nodo del subsistema para el proxy (por ejemplo, **Script ActiveX**).</span><span class="sxs-lookup"><span data-stu-id="41295-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="41295-128">Haga clic con el botón derecho en la cuenta de proxy que desee modificar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="41295-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="41295-129">En el cuadro de diálogo _nombre_proxy_**Propiedades de cuenta de proxy** , realice los cambios que considere necesarios en la cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="41295-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="41295-130">Para más información acerca de las opciones de este cuadro de diálogo, consulte [Crear un proxy del Agente SQL Server](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="41295-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="41295-131">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41295-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="41295-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41295-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="41295-133">Para modificar un proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41295-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="41295-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41295-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="41295-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="41295-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="41295-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="41295-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="41295-137">Para obtener más información, vea [sp_update_proxy &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="41295-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  
