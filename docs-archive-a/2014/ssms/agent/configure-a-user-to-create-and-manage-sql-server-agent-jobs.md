---
title: Configurar un usuario para crear y administrar trabajos del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677368"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="b6c64-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="b6c64-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="b6c64-103">En este tema se describe cómo configurar un usuario para crear o ejecutar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="b6c64-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="b6c64-104">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="b6c64-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="b6c64-105">**Para configurar un usuario para crear y administrar trabajos del Agente SQL Server, usando:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="b6c64-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b6c64-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b6c64-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b6c64-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b6c64-107">Security</span></span>  
 <span data-ttu-id="b6c64-108">Para configurar un usuario para crear o ejecutar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente, primero debe agregar un inicio de sesión de SQL Server existente o un rol msdb a uno de los siguientes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] roles fijos de base de datos del agente en la base de datos msdb: SQLAgentUserRole, SQLAgentReaderRole o SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="b6c64-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="b6c64-109">De forma predeterminada, los miembros de estos roles de la base de datos pueden crear sus propios pasos de trabajo que se ejecutan como ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="b6c64-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="b6c64-110">Si estos usuarios no administrativos desean ejecutar trabajos que ejecuten otros tipos de pasos de trabajo (por ejemplo, paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), necesitarán tener acceso a una cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="b6c64-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="b6c64-111">Todos los miembros del rol fijo de servidor sysadmin tienen permiso para crear, modificar o eliminar cuentas de proxy.</span><span class="sxs-lookup"><span data-stu-id="b6c64-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="b6c64-112">Para más información sobre los permisos asociados con estos roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b6c64-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b6c64-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="b6c64-113">Permissions</span></span>  
 <span data-ttu-id="b6c64-114">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="b6c64-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="b6c64-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6c64-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b6c64-116">**Para agregar un inicio de sesión de SQL o un rol msdb a un rol fijo de base de datos del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b6c64-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="b6c64-117">En el **Explorador de objetos**, expanda un servidor.</span><span class="sxs-lookup"><span data-stu-id="b6c64-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="b6c64-118">Expanda **Seguridad**y, a continuación, **Inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="b6c64-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="b6c64-119">Haga clic con el botón derecho en el inicio de sesión que desee agregar a un rol fijo de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b6c64-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="b6c64-120">En la página **asignación de usuarios** del cuadro de diálogo Propiedades de inicio de **sesión** , seleccione la fila que contiene `msdb` .</span><span class="sxs-lookup"><span data-stu-id="b6c64-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="b6c64-121">En **Miembros del rol de base de datos para: msdb**, active el rol fijo de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6c64-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="b6c64-122">**Para configurar una cuenta de proxy para crear y administrar pasos de trabajo del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b6c64-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="b6c64-123">En el **Explorador de objetos**, expanda un servidor.</span><span class="sxs-lookup"><span data-stu-id="b6c64-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="b6c64-124">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b6c64-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b6c64-125">Haga clic con el botón derecho en **Servidores proxy** y seleccione **Nuevo proxy**.</span><span class="sxs-lookup"><span data-stu-id="b6c64-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="b6c64-126">En la página **General** del cuadro de diálogo **Nueva cuenta de proxy** , especifique el nombre del proxy, el nombre de credencial y la descripción del nuevo proxy.</span><span class="sxs-lookup"><span data-stu-id="b6c64-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="b6c64-127">Tenga en cuenta que debe crear una credencial antes de crear un proxy del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6c64-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="b6c64-128">Para obtener más información sobre cómo crear una credencial, vea [crear una credencial](../../relational-databases/security/authentication-access/create-a-credential.md) y [crear credenciales &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6c64-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="b6c64-129">Seleccione los subsistemas correspondientes para este proxy.</span><span class="sxs-lookup"><span data-stu-id="b6c64-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="b6c64-130">En la página **Entidades de seguridad** , agregue o quite inicios de sesión o roles para conceder o quitar el acceso a la cuenta de proxy.</span><span class="sxs-lookup"><span data-stu-id="b6c64-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c64-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6c64-131">See Also</span></span>  
 [<span data-ttu-id="b6c64-132">Implementar la seguridad del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6c64-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
