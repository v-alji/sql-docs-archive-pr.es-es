---
title: Eliminar un proxy del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675105"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="d8052-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="d8052-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="d8052-103">En este tema se describe cómo eliminar una cuenta de proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8052-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d8052-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d8052-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8052-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d8052-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8052-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d8052-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d8052-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d8052-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8052-108">**Para eliminar una cuenta de proxy del Agente SQL Server, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="d8052-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="d8052-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8052-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d8052-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8052-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8052-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d8052-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d8052-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d8052-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d8052-113">Cuando elimine una cuenta de proxy del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , asegúrese de que el proxy no haga referencia a ningún paso de trabajo activo.</span><span class="sxs-lookup"><span data-stu-id="d8052-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="d8052-114">Para comprobar si existen pasos de trabajo que hacen referencia al proxy, haga clic con el botón derecho en el proxy, seleccione **Propiedades**y, luego, en el cuadro de diálogo _nombre_proxy_**Propiedades de cuenta de proxy** , seleccione la página **Referencias** .</span><span class="sxs-lookup"><span data-stu-id="d8052-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="d8052-115">Si elimina un proxy, en el cuadro de diálogo **Eliminar objeto** se le ofrece la posibilidad de volver a asignar todos los pasos de trabajo que utilizan ese proxy.</span><span class="sxs-lookup"><span data-stu-id="d8052-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="d8052-116">Las cuentas de proxy del Agente[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizan credenciales para almacenar información acerca de las cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="d8052-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="d8052-117">El usuario especificado en las credenciales debe tener el permiso "Iniciar sesión como proceso por lotes" en el equipo en que se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8052-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d8052-118">comprueba el acceso al subsistema de un proxy y da acceso al proxy cada vez que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8052-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="d8052-119">Si el proxy ya no tiene acceso al subsistema, el paso de trabajo da error.</span><span class="sxs-lookup"><span data-stu-id="d8052-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="d8052-120">De lo contrario, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suplanta al usuario especificado en el proxy y ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8052-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="d8052-121">Si el inicio de sesión del usuario tiene acceso al proxy o si el usuario pertenece a un rol con acceso al proxy, puede usarlo en un paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8052-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8052-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d8052-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8052-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="d8052-123">Permissions</span></span>  
 <span data-ttu-id="d8052-124">Solo los miembros del rol fijo de servidor **sysadmin** pueden crear, modificar o eliminar cuentas de proxy.</span><span class="sxs-lookup"><span data-stu-id="d8052-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8052-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8052-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="d8052-126">Para eliminar una cuenta de proxy del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8052-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="d8052-127">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la cuenta de proxy que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="d8052-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="d8052-128">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d8052-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d8052-129">Haga clic en el signo más para expandir la carpeta **Servidores proxy** .</span><span class="sxs-lookup"><span data-stu-id="d8052-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="d8052-130">Haga clic en el signo más para expandir el subsistema que contiene la cuenta de proxy que desee eliminar (por ejemplo, **Script de ActiveX)**.</span><span class="sxs-lookup"><span data-stu-id="d8052-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="d8052-131">Haga clic con el botón derecho en la cuenta de proxy que desea eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d8052-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="d8052-132">En el cuadro de diálogo **Eliminar objeto** , confirme que esté seleccionada la cuenta de proxy correcta.</span><span class="sxs-lookup"><span data-stu-id="d8052-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="d8052-133">Active la casilla **Volver a asignar a** para volver a asignar a otra cuenta los pasos de trabajo que hacen referencia a esta cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="d8052-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="d8052-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8052-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d8052-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8052-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="d8052-136">Para eliminar una cuenta de proxy del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8052-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="d8052-137">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8052-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8052-138">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d8052-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8052-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d8052-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="d8052-140">Para obtener más información, vea [sp_delete_proxy &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8052-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  
